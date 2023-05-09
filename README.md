# A unique social network: Connecting people through films and series
----
http://127.0.0.1:5000/


## Criteria A: Planning
### Problem definition
[Based on the interview and consultation with the client a problem has been identifid](#Appendix). The client is a films enthusiast, who spends most of their time consuming this type of media. She has noticed that many people around her do the same thing, thus spend most of their time without interacting with other people and struggle developing their social skills. There are over 200 streaming platforms but none of them has a space where users can directly interact with each other through the movies they love or create conversation by replying to each other's thoughts, promoting  alienation and an individualistic culture for young people. The client has noticed that a lot of people try to build interactions through internet forums, but this has proven to be counterproductive since the pages tend to be disorganized, they have visuals like images all over the place, people cant keep track of their posts and it's difficult to create direct interactions between users with such a large forum where all users post on the same page, making all interactions simultaneous and overwhelming. The client also doesn’t feel like most public forums make a good job protecting her personal data. 

### Rationale for proposed solution
Based on this problem, an adequate solution would be a specialized platform where people can communicate with each other through a shared interest in movies. The proposed network will allow users to interact with each other by uploading new titles, posting their thoughts on their profiles, and commenting on other users’ posts. To develop this website based network I will be using Python 3.8, Flask, HTML, CSS and SQLite. [1]()Python is versatile and highly efficient, having its own unit testing makes the process of coding a lot more efficient and its access to params such as flasks makes it ideal for web development. [2]()Flask is a framework to build web applications, it is simple and flexible using modular programming to keep the program lightweight and coherent. [3]()HTML is the best option for the development of this solution because it's supported by an extensive range of  browsers, meaning that it allows a wider connection between users. [4]()CSS will be used to design the website because in terms of design it has a wider range of formatting options and uses substantially less code, making the webpage less dense for browsers to support it. In order for the network to work properly the data provided by users must be stored, for this creating a database with a series of tables is a great option. [5]()SQLite does not need to read entire files, instead it reads and stores the necessary data, making it a great option for this website. 

### Design statement
I will create a film social network for building connections and creating interactions between users based on their favorite films. The network will allow users to upload new titles, post their thoughts about those titles on their profile and comment on others posts. The social network will be created using python 3.8, flask, html, css and SQLite (database). It will take around 4 weeks to complete based on the success criteria.

### Success criteria 
[Approved by client](#Appendix)

1. ```[issue: The client also doesn’t feel like most public forums make a good job protecting her personal data]``` The website has a secure registration system page with a password and email policy. The website has a login page where the user can log in to the network by using the information they previously registered.

2. ```[issue: difficult to create direct interactions between users with such a large forum where all users post on the same page]``` The website has a page for each user's profile, where their posts are displayed.

3. ```[issue: this has proven to be counterproductive since the pages tend to be disorganized]``` The website uses labels and a menu to guide the user thorugh the website.

4. ```[issue: people can't keep track of their posts]``` The website displays all users' posts on their profile.

5. ```[issue: none of them has a space where users can directly interact with each other through the movies they love or create conversation by replying to each other's thoughts]``` The website allows commenting (not posting) on others' posts. 

6. ```[issue: this has proven to be counterproductive since the pages tend to be disorganized, they have visuals like images all over the place]``` The Website has an individual display of the movies inserted by each user. 




## Criteria B: Design Overview

### System Diagram
![Copy of Project_3 system diagram](https://user-images.githubusercontent.com/111941990/231610635-36f3f27d-747a-4670-8ca9-4e08d1621306.png)
Fig 1.
### Flow Diagrams
### Algorithm for uploading information: flow diagram
![Add Film- Flow Diagram](https://user-images.githubusercontent.com/111941990/236772766-d3719b65-4242-43cf-9c09-544aba001649.png)
Fig 2. A flow diagram for a series of steps that allows the program to take a user's iput and save it into a database, to be used i othe parts of the code. This particualr flow diagram takes the add_film code as an example to show case the alogorithm, which is also used as in the app.route for profile to upload different inputs to the database.

### Algorithm for commenting: flow diagram. 

![Outsider_profile_view- Flow Diagram (3)](https://user-images.githubusercontent.com/111941990/236772419-15b9be8e-7733-47a3-800a-56d61000af8b.png)
Fig 3: A flow diagram for series of steps that allow the user input text to create and save a comment in the database, to then display it in the selected user's profile.

### UML Diagram
![UML_diagram (3)](https://user-images.githubusercontent.com/111941990/236962983-2aac0f47-1c3c-4a37-b88e-6eb2cfc69da4.png)
Fig 4. A diagram taht visually represents the main classes of a program.

### ER Diagram 
![Copy of Er diagram](https://github.com/DaniSofiaG/project_4/assets/111941990/2aaaac87-ff02-4121-aba3-7fa20caec358)
Fig 5. This an entity-relationship diagram, it illustrateds the relationships between data in the programs database, in this case "social_ned.db".
## Test Plan
|    |                    Description of the Test                   |     Type     |                                                                  Test Steps                                                                 |                                                                                                              Planned Output                                                                                                             |
|----|:------------------------------------------------------------:|:------------:|:-------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|  1 |          Create an account through the register page         | Unti testing |              1. Click on "Register" on the homepage 2. Fill out the registration form with your information 3.Click "Register".             |                                                                                   The user's information is recorded in the database for the new user.                                                                                  |
|  2 |                       Password hashing                       | Unti testing |                               [Passwords are automatically hashed when entered during registration or login.]                               |                                                                               The password is not shown in the database, instead it is only shown hashed.                                                                               |
|  3 | Try to login to the application using the account registered | Unti testing |               1. Click on "Login" on the homepage 2. Enter your email and password used during registration 3. Click "Login".               |                                                                                        The user can log in using the information they registered.                                                                                       |
|  4 |                         Film display                         | Unti testing |               [After logging in, the user is automatically redirected to the film page where they can see all of their films.]              |                                                 When the correct information is logged in the user is automatically redirected to the film page, where they can see all of their films.                                                 |
|  5 |                      Film display update                     | Unti testing |                1. Click the "Add film" button on the film page 2. Fill out the form with the film information 3.Click "Post".               |                                                           After submitting all valid information the image display will automatically update with the new film the user added.                                                          |
|  6 |                         Post creation                        | Unti testing | 1. In the profile page click the "Create post" button on your profile page 2. Fill out the form with ths posts information 3. Click "Post". |                                                                               The new post is added to the user's profile and can be seen by other users.                                                                               |
|  7 |                       Display of posts                       | Unti testing |                   [The user's profile page is automatically updated with the new post without needing to reload the page.]                  |                                                                             All posts can be seen on the user's profile with no need of reloading the page.                                                                             |
|  8 |                       Comment creation                       | Unti testing |   1. Click the "Add comment" button on another user's profile page 2. Fill out the form with your comment information 3. Click "Comment".   |                                                                                        Only users who don't own the profile can create comments.                                                                                        |
|  9 |                      Display of comments                     | Unti testing |                                           [All users can see the comments in all user's profiles.]                                          |                                                                                          All users can see the comments in all user's profiles.                                                                                         |
| 10 |                     Table with all users                     | Unti testing |                                                1. Click the "All Users" button on the website                                               |                                                              The user's can see a table with all user accounts, but they cannot see the password or hashing for the users.                                                              |
| 11 |                 Access to each user's profile                | Unti testing |                                        1. Click on another user's username on the "All Users" table                                         |                                                      User's can access a view only form of each other's profiles where they can't edit or create posts, but they can add comments.                                                      |
|    |                            Log out                           | Unti testing |                                                 1. Click the "Log Out" button on the website                                                | Users can log out from their account. If someone who hasn't logged in tries to access any of the pages in the social network, though URL trying to avoid login and registration, they will automatically be returned to the login page. |


## Recorded Tasks
| Task No |                                Planned Action                                |                                                                                            Planned Outcome                                                                                           | Time estimate |  Date  | Criterion |
|:-------:|:----------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------:|:------:|:---------:|
|    1    |                        Planning: Identify the problem                        |                                            Understanding the problem and the client's needs, note it on the problem definition of the git hub reposiotry.                                            |     10min     |  Apr 4 |     A     |
|    2    |             Planning: Brainstroming for solutions to the problem             |                                                           Using the problems described, ideate a solution that adresses the clients issues.                                                          |     7 min     |  Apr 5 |     A     |
|    3    |                        Planning: Proposing a solution                        |                        After brainstorming, revise all the ideas considering the issue and write a proposed solution on the doucmentation that adresses the client's issues.                         |     15 min    | Apr 10 |     A     |
|    4    |                      Planning: Defining succes criteria                      | Based on my propose solution and the problem identify and record a set of success critrias that will guide the process of the creation of the unique social network. The success criteria have to be |     10 min    | Apr 11 |     A     |
|    5    |                        Design: Work on system diagram                        |                                                  Using google drawings make a system diagram that illustrates the modules and components in a system                                                 |     15 min    | Apr 12 |           |
|    6    |                             Design: Testing plan                             |                                                     Build a testing plan for using black box to use when code later on in the development process                                                    |     20 min    | Apr 13 |           |
|    7    |                          Design: Work on ER diagram                          |                                                                                                                                                                                                      |               | Apr 14 |           |
|    8    |                          Design: Start flow charts                           |                                                Choose the first diagram of my code that I will make into a fow diagram and draw the first flow diagram                                               |     25 min    | Apr 14 |           |
|    9    |                                                                              |                                                                                                                                                                                                      |               | Apr 14 |           |
|    10   |                                                                              |                                                                                                                                                                                                      |               | Apr 14 |           |
|    11   |                                 registration                                 |                                                                                                                                                                                                      |     40 min    | Apr 15 |           |
|    12   |                         choose file in profile posts                         |                                                                                                                                                                                                      |               | Apr 16 |           |
|    13   |                                                                              |                                                                                                                                                                                                      |               | Apr 17 |           |
|    14   |                                                                              |                                                                                                                                                                                                      |               | Apr 18 |           |
|    15   |                       Development: image upload method                       |                                                                                                                                                                                                      |               | Apr 19 |           |
|    16   |                       Development: image upload button                       |                                                                                                                                                                                                      |               | Apr 19 |           |
|    17   |               Development: updating and creating html templates              |                                                                                                                                                                                                      |               | Apr 19 |           |
|    18   |                     Development: solving database issues                     |                                                                                                                                                                                                      |               | Apr 19 |           |
|    19   |                        Design: creating a testing plan                       |                                                                                                                                                                                                      |               | Apr 19 |           |
|    20   |              ____: unit testing for login and registrationsystem             |                                                                                                                                                                                                      |               | Apr 19 |           |
|    21   |                      ____: unit testing for posting page                     |                                                                                                                                                                                                      |               | Apr 19 |           |
|    22   |                      ____: unit testing for image upload                     |                                                                                                                                                                                                      |               | Apr 20 |           |
|    23   |              Development: identify issues with the image upload              |                                                                                                                                                                                                      |               | Apr 20 |           |
|    24   |                   Development: solve issues of image upload                  |                                                                                                                                                                                                      |               | Apr 20 |           |
|    25   |                  ____: second unit testing for image upload                  |                                                                                                                                                                                                      |               | Apr 20 |           |
|    26   |                     Planning: reviewing success criteria                     |                                                                                                                                                                                                      |               | Apr 21 |           |
|    27   |                      Planning: imroving success criteria                     |                                                                                                                                                                                                      |               | Apr 22 |           |
|    28   | Development: change image upload to use file name to work with the database  |                                                                                                                                                                                                      |               |        |           |
|    29   |                  Development: individual user prifile pages                  |                                          Make the html pages be individual to each user, intead of them working as a general page with posts from all users                                          |               |        |           |
|    30   |              Evaluate functionality and make changes to my code              |                                                                     Change image upload form field to text input insteasd of file                                                                    |     7 min     |        |           |
|    31   |                                                                              |                                                                                                                                                                                                      |               |        |           |
|    32   |                                                                              |                                                                                                                                                                                                      |               |        |           |
### ER Diagram


## Criteria C: Development

### List of techniques
- If statements
- Forloops
- Variables
- CSS Styling
- Html
- Functions
- 
- Connecting to a database
- Arrays
- OOP

### Computational Thinking in Code

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

The add film route defines the function add_film(). First, the function connects to the “social_net.db” using the database_worker import from the programs library. Using the user_id the route takes the user to the “add_film” page, where they’ll find a form for inputting “title”, “director” and “image”. Then it declasers an empty array for pasts. The purpose of this function is to get 3 user inputs from the form when uploaded using the method ‘POST’ that was initially defined in the methods of the route, then if the the inputs are bigger than 0 in length they a query “new_film” to save them as strings into the table “films” of the “social_net.db” along with integer type input user_id is executed, and then the user is redirected to the “films” page. If the information submitted through ‘POST’ is not valid, the function will look for the user’s id and redirect them to their personal “add_films” page again.  The process of doing this part of the code was particularly challenging because the input for the image field was first intended to take a file type input instead of a text string and so it was saved into the database as the file name, this was a problem because the information on this database is used retrieved later in the program so that it can be displayed as an actual image for the user to see of the films page, because at first it was saved as a file name the program couldn’t display the images in the corresponding html, unless each was individually uploaded into the statics folder of the flask project. The problem was solved changing the input type to a stirring and requesting the use of a link as the input, instead of a file. The link is then saved to the database along with the other inputs as a string text, so later in the program it can be used in the ‘films’ function html as a source for an image and displays all newly uploaded images without needing to directly upload any files to the statics folder. 


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
The films route defines the function “films”. First, the function connects to the “social_net.db” using the database_worker import from the programs library and sets user, and films to value “None” in case the query that is later in the code, then it defines user as a query to search for the user_id of the user that is in using the webpage. If the program doesn’t find the user in the database it can return “None”, instead of launching an error. Then if the database finds a user, the “films” query is defined as all data in the “films” table of the “social_net.db” database and the user is set to user[0].It sets user to be user[0] because in the table ‘films’ in the database the user identification number (user_id) is in the column 0 of the table. There were not many direct challenges from this section of the code, except for those from the corresponding html, which were solved indirectly when working on the “add_films” function previously explained.

## Films HTML and CSS
### Films html
```.html
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
### CSS for films
```.css
section{
    display:flex;
    width: 1380px;
    height: 430px;

}

.img-flex{
    width: 0px;
    flex-grow: 1;
    object-fit: cover;
    opacity: 0.9;
    transition: 0.5s ease;
}

section img:hover {
    cursor: pointer;
    width: 300px;
    opacity: 1;
    filter: contrast(120%);
}
```
The css and html for films create a image interactive display page for each individual user. The HTML code first uses an if statement to ensure that each user only sees their own uploaded data, specifically the images that they added through the "add_film" function. If the if statement finds no user in the database, the "film" function (previously explained) will display the message "User does not exist." Next, a section of buttons is displayed, which allows the user to navigate to various pages of the website. The if statement is then closed. Following this, a new if statement is opened with the title "These are your films." Using a for loop, the code searches the "film" table's third column in the database where links to images are stored when a user adds a film, then it closes the for loop. Using that for loop, all the links corresponding to user’s uploaded images are taken as image sources for the image input, and then they are displayed as images in a row. Additionally, an "on-click" action makes all the images clickable, allowing the user to navigate to their personal profile page. Through CSS, the image input uses a class to create a flexible box display that animates the film images when hovered over. If the users film inputs were none then it would simply say “You don’t have films yet!!” and end the if statement. Using the flex display, despite not being a complicated element to create, if made figuring out how to make images functional buttons challenging, thesis is because the animation put on the flex display in the css would stop working if a href link or direction was put wrapping the for loop or inside the image input. The “on-click” action was used to solve the problem. “On-click” made the button creation process for efficient as it didn't require much alteration to the html or code to work, rather it used the name of the html page to direct the user and it used the already defined “user_id=user” input to take each user only to their corresponding profile page. 

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
When directed to their personal profile page from the clickable image display in the film html using the and “profile” and user_id on-click the route takes the user to the “profile” page, where they’ll find another form for inputting “title” and “content”. The purpose of this function is to get 2 user inputs from the form when uploaded using the method ‘POST’ that was initially defined in the methods of the route, then, if the the inputs are bigger than 0 in length a different query “posts” is executed to upload the “title” and “content” data to de “social_net.db” table for “posts” and its is saved along the user_id as integer, and then the user is redirected to the updated “profile” page with the new posts on it. If the information submitted through ‘POST’ is not valid, the function will look for the user’s id and redirect them to their personal “add_films” page again.  Then the profile defines user, posts and comments as “None” in case the program can’t find anything in the database for the user_id it doesn’t create an error and the profile can simply show no inputs. It sets users and comments to search whatever corresponds to the user logged-in in their corresponding tables. If a user is found for both posts and comments, then they are displayed in the profile page, the posts in a table format and the comments in a scrollable container. At first the profile page would only display the posts and the form to add them, however as part of the development and based on the client meetings its was important to have a way to connect users and so instead of having a comment section on a completely different section of the site, it was decided that it would be displayed on the profile page. 


### Outsider Profile View: Commenting
```.py
@app.route('/outsider_profile/<user_id>', methods=['GET', 'POST'])
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
The outsider profile page created through the profile route is in essence a copy of the profile page as its purpose is to show all  content on the profile page, without allowing external users to edit the user’s profile posts, but having a seduction for them to create and upload comments to other user’s profile, which promotes interaction with others, tackling the user’s problems. First, the outsider_profile_view function connects to the “social_net.db” using the database_worker import from the programs library. Then it defines the user, posts, posts_id and comments are defined as database searches where user_id is the same as th euser_id of the logged-in user, they all retrieve all data from their corresponding tables,except for post_id that retrieved on the id from the “posts” table. Like the add_film and profile functions of this program, the second part of the outsider_porfile_view uses the same methods to retrieve information from comment text field using the method ‘POST’ that was initially defined in the methods of the route, then if the the input is bigger than 0 in length then a query “new_comment” is executed to save them as strings into the table “comments” of the “social_net.db” along with integer type input user_id executed, and then the user is redirected to the updated “outside_profile_viewr” page. The outsider profile view was one of the most challenging parts of the code, since its developments started became unorganized due to issues in data migration when the computer in which the site was being built became broke and so there was an incomplete data transfer of a part of the code, that made the development process confusing and unorganized. To overcome the issues with data migration the outsider_profiel_view was completely erased and built from scratch again. 

## Criterion D: Functionality and Extensibility

## Criterion E: Evaluation

# Appendix
### Client Consultation 
<img width="996" alt="Screen Shot 2023-05-10 at 6 22 38" src="https://github.com/DaniSofiaG/project_4/assets/111941990/998852b3-8514-460c-890c-42324a6f307e">
<img width="998" alt="Screen Shot 2023-05-10 at 6 22 45" src="https://github.com/DaniSofiaG/project_4/assets/111941990/fc15f216-eb58-4286-bbad-95346e18a1ad">
<img width="994" alt="Screen Shot 2023-05-10 at 6 22 49" src="https://github.com/DaniSofiaG/project_4/assets/111941990/f189681e-4716-452a-a6bd-2863fb896882">
<img width="975" alt="Screen Shot 2023-05-10 at 6 22 54" src="https://github.com/DaniSofiaG/project_4/assets/111941990/386a06f7-59ae-4e75-8630-931520a9b111">
<img width="968" alt="Screen Shot 2023-05-10 at 6 23 00" src="https://github.com/DaniSofiaG/project_4/assets/111941990/629a51ba-8f33-44d4-9c16-79bfcbca2ef4">
<img width="958" alt="Screen Shot 2023-05-10 at 6 23 06" src="https://github.com/DaniSofiaG/project_4/assets/111941990/2313bd0a-2df7-465e-aca2-6e1401436642">
<img width="989" alt="Screen Shot 2023-05-10 at 6 23 11" src="https://github.com/DaniSofiaG/project_4/assets/111941990/1d34268f-b9e2-4be7-a094-217108b92ef0">
<img width="984" alt="Screen Shot 2023-05-10 at 6 23 16" src="https://github.com/DaniSofiaG/project_4/assets/111941990/631f2571-4500-4b3f-bd47-86403d9af7d4">

### Client Interview Summanry







### Client consultation


