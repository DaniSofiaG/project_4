# A unique social network: Connecting people through films and series
----

## Criteria A: Planning
### Problem definition
My client is a films and series enthusiast, who spends most of their time consuming this type of media. She has noticed that many people around her do the same thing, thus spend most of their time without interacting with other people and struggle developing their social skills. There are over 200 streaming platforms but none of them has a space where users can directly interact with each other through the movies they love or create conversation by replying to each other's thoughts, promoting  alienation and an individualistic culture for young people. The client has noticed that a lot of people try to build interactions through internet forums, but this has proven to be counterproductive since the pages tend to be disorganized, people cant keep track of their posts and it's difficult to create direct interactions between users with such a large forum where all users post on the same page, making all interactions simultaneous and overwhelming. The client also doesn’t feel like most public forums make a good job protecting her personal data. 

### Rationale for proposed solution
Based on this problem, an adequate solution would be a specialized platform where people can communicate with each other through a shared interest in movies and series. The proposed network will allow users to interact with each other by uploading new titles, posting their thoughts on their profiles, and commenting on other users’ posts. To develop this website based network I will be using Python 3.8, Flask, HTML, CSS and SQLite. [1]Python is versatile and highly efficient, having its own unit testing makes the process of coding a lot more efficient and its access to params such as flasks makes it ideal for web development. [2]Flask is a framework to build web applications, it is simple and flexible using modular programming to keep the program lightweight and coherent. [3]HTML is the best option for the development of this solution because it's supported by an extensive range of  browsers, meaning that it allows a wider connection between users. [4]CSS will be used to design the website because in terms of design it has a wider range of formatting options and uses substantially less code, making the webpage less dense for browsers to support it. In order for the network to work properly the data provided by users must be stored, for this creating a database with a series of tables is a great option. [5]SQLite does not need to read entire files, instead it reads and stores the necessary data, making it a great option for this website. 

### Design statement
I will create a film social network for building connections and creating interactions between users based on their favorite films. The network will allow users to upload new titles, post their thoughts about those titles on their profile and comment on others posts. The social network will be created using python 3.8, flask, html, css and SQLite (database). It will take around 4 weeks to complete based on the success criteria.

### Success criteria

1. ```[issue: The client also doesn’t feel like most public forums make a good job protecting her personal data]``` The website has a secure registration system page with a password and email policy. The website has a login page where the user can log in to the network by using the information they previously registered.

2. ```[issue: difficult to create direct interactions between users with such a large forum where all users post on the same page]``` The website has a page for each user's profile, where their posts are displayed.

3. ```[issue: this has proven to be counterproductive since the pages tend to be disorganized]``` The website has a layout that makes organization simple and easy to understand for the users. 

4. ```[issue: people can't keep track of their posts]``` The website displays all users' posts on their profile.

5. ```[issue: none of them has a space where users can directly interact with each other through the movies they love or create conversation by replying to each other's thoughts]``` The website allows commenting (not posting) on others' posts. 





## Criteria B: Design Overview

### System Diagram
![Copy of Project_3 system diagram](https://user-images.githubusercontent.com/111941990/231610635-36f3f27d-747a-4670-8ca9-4e08d1621306.png)

### Flow Diagrams

### UML Diagrams

### ER Diagram


## Criteria C: Development

### List of techniques
- If statements
- Forloops
- Variables
- Functions
- Connecting to a database

### Computational Thinking in Code

#### Registration System
```.py
@app.route('/register', methods=["GET", "POST"])
def register():
    msg = ''
    if request.method == 'POST':
        email = request.form['email']
        password = request.form['password']
        hash = encrypt_password(password)
        db = database_worker("social_net.db")
        query = f"INSERT into users(email, password) values('{email}', '{hash}')"
        db.run_save(query)
        db.close()

    else:
        msg = "Register"
    return render_template("register.html", message=msg)""" (ADD PASWORD POLICY)```
```
```.diff
```
    
### Add films
```.py
@app.route('/add_film/<user_id>', methods=['GET', 'POST'])
def add_film(user_id: int):
    db = database_worker("social_net.db")
    posts = []
    if request.method == 'POST':
        title = request.form['title']
        director = request.form['director']
        image = request.form['image']
        # save image on a folder of every user
        if len(title) > 0 and len(director) > 0 and len(image) > 0:
            new_film = f"INSERT into films(title, director, image, user_id) values ('{title}', '{director}', '{image}', '{user_id}')"
            db.run_save(query=new_film)
            return redirect(url_for('films', user_id=user_id))
    else:
        user, new_film = None, None
        user = db.search(f"SELECT * from users where id = {user_id}")

        if user:
            posts = db.search(f"select * from films where user_id={user_id}")
            user = user[0]  # remember db.sear return a list
        return render_template("add_film.html", user=user, posts=posts)
```
```.diff
```

### Films 
```.py
@app.route('/films/<user_id>', methods=['GET', 'POST'])
def films(user_id: int):
    db = database_worker("social_net.db")

    user, films = None, None
    user = db.search(f"SELECT * from users where id = {user_id}")

    if user:
        films = db.search(f"SELECT * FROM films where user_id={user_id}")
        user = user[0]
    return render_template("films.html", user=user, films=films)
```
```.diff
```

### Films html
```.py
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">

    {% if user %}
    <title>This are your films {{ user[1] }}</title>
    {% else %}
    <title>User does not exist</title>
    {% endif %}
    <link rel="stylesheet" href="/static/login_style.css">

</head>
<body>


{% if user %}
    <h1>This are your films {{ user[1] }}</h1>
    <section>
        {% if films %}
            {% for film in films %}
                <img class="img-flex" src="{{ film[3] }}" alt="{{ film[1] }}" onclick="location.href='{{ url_for("profile",user_id=user[0]) }}'">
            {% endfor %}
        {% else %}
            <p>You don't have films yet!!!</p>
        {% endif %}
    </section>


{% else %}
    <p> You don't have films yet!</p>
{% endif %}

<input type="button" class="new_button" value="Add films!!!" onclick="location.href='{{ url_for("add_film",user_id=user[0])}}'">

</body>
</html>
```
```.diff
```

### Profile
```.py
@app.route('/users/<user_id>', methods=['GET', 'POST'])
def profile(user_id: int):
    db = database_worker("social_net.db")

    if request.method == 'POST':
        title = request.form['title']
        content = request.form['content']
        if len(title) > 0 and len(content) > 0:
            new_post = f"INSERT into posts (title, content, user_id) values('{title}','{content}',{user_id})"
            db.run_save(query=new_post)
            return redirect(url_for('profile', user_id=user_id))

    user, posts, comments = None, None, None
    user = db.search(f"SELECT * from users where id = {user_id}")
    comments = db.search(f"SELECT * from comments where user_id = {user_id}")


    if user:
        posts = db.search(f"select * from posts where user_id={user_id}")
        user = user[0]  # remember db.sear return a list
    return render_template("profile.html", user=user, posts=posts, comments=comments)
```
```.diff
```

### Outsider Profile View: Commenting
```.py
@app.route('/outsider_profile/<int:user_id>', methods=['GET', 'POST'])
def outsider_profile_view(user_id:int):
    db = database_worker("social_net.db")

    user, posts, posts_id = None, None, None
    user = db.search(f"SELECT * from users where id ={user_id}")
    posts = db.search(f"SELECT * from posts where id = {user_id}")
    posts_id = db.search(f"SELECT id from posts where user_id = {user_id}")
    comments = db.search(f"SELECT * from comments where user_id = {user_id}")

    if request.method == 'POST':
        comment = request.form['comment']
        if len(comment) > 0:
            new_comment = f"INSERT into comments (comment, user_id) values('{comment}', {user_id})"
            db.run_save(query=new_comment)
            return redirect(url_for('outsider_profile_view', user_id=user_id))
    return render_template('outsider_profile_view.html', user=user, posts=posts, posts_id=posts_id, comments=comments, user_id=user_id)
```
```.diff
```

