Download Link: https://assignmentchef.com/product/solved-cs1xa3-project1-socialnetwork
<br>
<h2>Add The Project03 Template To Your Repo</h2>

<ul>

 <li>You can download the starting template project from <a href="https://github.com/dalvescb/django_templates">https://github.com/dalvescb/django_ </a><a href="https://github.com/dalvescb/django_templates">templates</a><a href="https://github.com/dalvescb/django_templates">,</a> under Project03</li>

 <li>Simply copy the Project03 folder in its entirety into your own github repo, i.e so there now exists a folder CS1XA3/Project03</li>

</ul>

<h2><a name="_Toc8569"></a>1.2           Replace macid with you’re Mac ID (necessary to run on mac1xa3.ca)</h2>

<ul>

 <li>Search and replace instances of macid with you’re actually McMaster ID in the following files</li>

 <li>Project03/Project03/urls.py</li>

 <li>Project03/Project03/settings.py</li>

</ul>

<h2><a name="_Toc8570"></a>1.3           Commit and Push</h2>

<ul>

 <li>Add and commit this folder (to the master branch) with the following message EXACTLY “Initial Project03 Commit”</li>

 <li>Push (to the master branch) to GitHub</li>

</ul>

<h2><a name="_Toc8571"></a>1.4           Create a Branch</h2>

<ul>

 <li>Create a branch called project03</li>

 <li>Push the branch to github (i.e git push origin project03)</li>

 <li>Work from the project03 branch and only merge with master when your ready to submit</li>

</ul>

<h2><a name="_Toc8572"></a>1.5           Work From Your Private Directory When On mac1xa3.ca</h2>

<ul>

 <li>NOTE I highly recommend completing this project from your local machine, and then testing it on mac1xa3.ca when you are finished. However the project MUST RUN FROM MAC1XA3.CA as this is where it will be marked, so do not wait too close to the due date to make sure it works there</li>

 <li>When working/running on the mac1xa3 server, you must keep your repo inside of the directory located in $HOME/private on the mac1xa3.ca server</li>

 <li>WARNING not doing so or changing the default permissions on the private directory will be considered academic dishonesty</li>

</ul>

<h2><a name="_Toc8573"></a>1.6           Submission</h2>

<ul>

 <li>When you are ready to submit, merge your project03 branch with master</li>

 <li>Make sure you push to Github</li>

 <li>Make sure an up to date version of your repo is cloned on the mac1xa3.ca server (i.e in $HOME/private/CS1XA3)</li>

</ul>

<h2><a name="_Toc8574"></a>1.7           Running the Server</h2>

<ul>

 <li>Without completing any of the objectives, you can run the server as is on your local machine with python manage.py runserver localhost:8000</li>

 <li>then going to localhost:8000/e/macid/ in your browser</li>

 <li>For instructions on running the server on mac1xa3.ca, see the README on <a href="https://github.com/dalvescb/django_templates/tree/master/user_models_2">https://github.com/ </a><a href="https://github.com/dalvescb/django_templates/tree/master/user_models_2">dalvescb/django_templates/tree/master/user_models_2</a></li>

</ul>

<h1><a name="_Toc8575"></a>2           Project Overview</h1>

The goal of this project is to complete the social media like site provided in the Project03 template. The site consists of the following pages:

<ul>

 <li>login app

  <ul>

   <li>login page (Project03/login/templates/login.djhtml)</li>

   <li>signup page (Project03/login/templates/signup.djhtml)</li>

  </ul></li>

 <li>social app

  <ul>

   <li>account settings page (Project03/social/templates/account.djhtml)</li>

   <li>messages display page (Project03/social/templates/messages.djhtml)</li>

   <li>people/friend lookup page (Project03/social/templates/people.djhtml)</li>

  </ul></li>

</ul>

<h2><a name="_Toc8576"></a>2.1           Project Database</h2>

All of the models (i.e the database) needed for the website have already been created in

<ul>

 <li>Project03/social/models.py class Interest(models.Model):</li>

</ul>

<em># Related to UserInfo as m2m relation, holds interests as strings </em>class UserInfoManager(models.Manager):

<em># implements the create_user_info method for creating UserInfo entries </em>class UserInfo(models.Model):

<em># A 1-to-1 relation with the built-in User objects, adds additional info </em>class Post(models.Model):

<em># holds posts made by users and displayed in the messages page </em>class FriendRequest(models.Model):

<em># holds friend requests from one User to another</em>

<h2><a name="_Toc8577"></a>2.2           Project Templates</h2>

The entire project makes use of a base template base.djhtml in Project03/templates/base.djhtml that extends the <a href="https://www.w3schools.com/w3css/tryit.asp?filename=tryw3css_templates_social&amp;stacked=h">w3schools social media template.</a> By default, i.e un-extended, it provides.

<ul>

 <li>links to a variety of w3schools stylesheets and meta page definitions (use the css block to extend)</li>

 <li>an import link for JQuery</li>

 <li>a navbar with an icon on the right that links to the account settings page (use the navbar_contents block to extend)</li>

 <li>a footer</li>

 <li>three empty column sections (use the left, middle and right column blocks to extend) The base template is extending by</li>

 <li>djhtml (implements middle_column to provide login form)</li>

 <li>djhtml (should implement middle_column to provide signup form)</li>

 <li>djhtml (implements left_column to provide account info, and navbar to provide links to account, messages, people pages)</li>

</ul>

The social_base.djhtml template implements the right_column block and is extended by

<ul>

 <li>djhtml (should implement middle / right columns to provide account settings forms)</li>

 <li>djhtml (should implement middle / right columns to show posts / friends list respectively)</li>

 <li>djhtml (should implement middle / right columns to show unfriended people / friend requests respectively)</li>

</ul>

<h1><a name="_Toc8578"></a>3           Project Objectives</h1>

Perform each of the following objectives to complete the project. Most objectives provide a fair amount of guidance, but you may delete/add as much code as you like to achieve the attended effect of the objective.

<ul>

 <li>TIP: Follow the TODO Objective N comments in the codebase</li>

</ul>

<h2><a name="_Toc8579"></a>3.1           Objective 1: Complete Login and SignUp Pages (5 points)</h2>

<ul>

 <li>There are login and signup pages already set up under the Project03/login app</li>

 <li>By default, the URL /e/macid/ will route to the login</li>

 <li>In order to login you need to create a UserInfo entry ( NOTE it is not sufficient to create just a User object)</li>

 <li>You can create a new {{{color(blue,UserInfo)}} object manually from the shell by running the commands (remember to run migrations first)</li>

</ul>

python manage.py shell

&gt;&gt;&gt; from social import models

&gt;&gt;&gt; models.UserInfo.objects.create_user_info(username=’TestUser’,password=’1234′) &gt;&gt;&gt; exit

<ul>

 <li>The login form is already completed, click the Login button to try logging in, then click the Logout button in the Navbar to logout</li>

 <li>If you click the Create An Account button, you’ll be redirected to a mostly blank page</li>

 <li>Implement this page by:

  <ul>

   <li>Add the appropriate code to the function def signup_view in Project03/login/views.py to render djhtml with an appropriate form</li>

   <li>Add the appropriate code in Project03/login/templates/signup.djhtml to display a form for creating a new user</li>

   <li>Add appropriate code to handle the POST request sent by the form to create a new user (i.e automate the code above for creating a UserInfo object)</li>

   <li>After creating a new user, automatically log the user in and redirect to the messages page</li>

  </ul></li>

</ul>

<h2><a name="_Toc8580"></a>3.2           Objective 2: Adding User Profile and Interests (5 points)</h2>

<ul>

 <li>The template djhtml renders the left_column used by messages.djhtml,people.djhtml and account.djhtml</li>

 <li>When each of the above templates are rendered in Project03/social/views.py (see messages_view, people_view and account_view respectively), they are given the currently logged in UserInfo object via a variable (and hence djhtml has access to it as well)</li>

 <li>djhtml currently displays a statically included fake Profile and Interests</li>

 <li>Edit Project03/social/templates/social_base.djhtml to implement a real Profile and Interests corresponding to the currently logged in user by using Django Template Variables</li>

 <li>See the UserInfo class in Project03/social/models.py for details on the attributes available</li>

</ul>

<h2><a name="_Toc8581"></a>3.3           Objective 3: Account Settings Page</h2>

<ul>

 <li>Clicking the top right icon on the Navbar brings you to the Account Settings Page, rendered by

  <ul>

   <li>the function def account_view in Project03/social/views.py</li>

   <li>the template Project03/social/templates/account.djhtml</li>

  </ul></li>

 <li>Currently the page is mostly blank (besides the content already rendered by the base templates)</li>

 <li>Edit the above function / template to:

  <ul>

   <li>Provide forms for changing the users current password</li>

   <li>Provide forms for updating user info, i.e employment, location, birthday, interests (each interest submission should add to the list of current interests)</li>

   <li>Handle POST requests sent by the form’s to update the UserInfo object accordingly</li>

  </ul></li>

</ul>

<h2><a name="_Toc8582"></a>3.4           Objective 4: Displaying People List</h2>

<ul>

 <li>Clicking the people icon on the Navbar brings you to the People Page, rendered by

  <ul>

   <li>the function def people_view in Project03/social/views.py</li>

   <li>the template Project03/social/templates/people.djhtml</li>

   <li>the javascript code Project03/social/static/people.js</li>

  </ul></li>

 <li>Currently the middle column displays a single static fake person and a More button</li>

 <li>Edit the above function / template to:

  <ul>

   <li>Display actual User’s in the middle column who ARE NOT FRIENDS of the current user (HINT use a for loop in the djhtml template to replicate the current div)</li>

   <li>The page should start out displaying only a certain amount of people (say 1), then display more by clicking the More The amount of people displayed should reset when the user logs out</li>

   <li>Note: the more button is already linked to send an AJAX POST through javascript (see Project03/social/static/people.js) to def more_ppl_view, and then reload the page on success</li>

   <li>HINT use a session variable to keep track of how many people to display</li>

  </ul></li>

</ul>

<h2><a name="_Toc8583"></a>3.5           Objective 5: Sending Friend Requests</h2>

<ul>

 <li>The right column of djhtml should display friend requests to the current user (currently only displays a single static fake friend request)</li>

 <li>All Friend Request buttons are linked to a JQuery event in js, which uses its id to send a POST request to the function def friend_request_view</li>

 <li>Edit the djhtml template to configure the Friend Request button so it’s id contains the user who sent the friend request</li>

 <li>Edit the function friend_request_view to handle the POST by inserting an appropriate entry to the FriendRequest model</li>

 <li>Now edit def people_view and djhtml to render actual friend requests</li>

</ul>

<h2><a name="_Toc8584"></a>3.6           Objective 6: Accepting / Declining Friend Requests</h2>

<ul>

 <li>The Friend Requests displayed in Objective 5 contain Accept and Decline buttons</li>

 <li>Edit djhtml so that the id’s of those buttons contain the username of the user who sent the Friend Request</li>

 <li>Edit js so that pushing either Accept or Decline buttons sends a POST to accept_decline_view with the appropriate button id</li>

</ul>

– HINT: copy how the friendRequest function works, it will be very similar

<ul>

 <li>Edit accept_decline_view to handle the POST request, it should delete the corresponding FriendRequest entry, and if the request was accepted should update BOTH USERS friends relation in the UserInfo table</li>

</ul>

<h2><a name="_Toc8585"></a>3.7           Objective 7: Displaying Friends</h2>

<ul>

 <li>Clicking the message icon on the Navbar brings you to the Message Page, rendered by

  <ul>

   <li>the function def messages_view in Project03/social/views.py</li>

   <li>the template Project03/social/templates/messages.djhtml</li>

   <li>the javascript code Project03/social/static/messages.js</li>

  </ul></li>

 <li>Currently, the right column shows only a single static fake friend</li>

 <li>Edit djhtml to display all of the friends of the current user

  <ul>

   <li>HINT: iterative over the objects returned by all of the friends relation in the user_info variable</li>

  </ul></li>

</ul>

<h2><a name="_Toc8586"></a>3.8           Objective 8: Submitting Posts</h2>

<ul>

 <li>The top of the middle column of the Messages Page contains a text field (id post-text) and button (id post-button for submitting posts</li>

 <li>Edit js to submit a AJAX POST request when post-button is clicked, sending the contents of post-text to post_submit_view</li>

 <li>Reload the page upon a success response</li>

 <li>Edit post_submit_view to handle the post submission, by adding a new entry to the Post model</li>

</ul>

<h2><a name="_Toc8587"></a>3.9           Objective 9: Displaying Post List</h2>

<ul>

 <li>Currently the Messages Page displays only a single static fake Post in the middle column (under the submit post div)</li>

 <li>Edit djhtml to display real posts given by messages_view when rendering the template</li>

 <li>Edit the function messages_view to query for posts, sort posts by newest and to oldest

  <ul>

   <li>HINT: use order_by on the primary key)</li>

  </ul></li>

 <li>The page should start out displaying only a certain amount of Posts (say 1) and should display incrementally more as the More button is clicked (just like in Objective 4)</li>

 <li>The More button is already configured to send a post to more_post_view

  <ul>

   <li>HINT use a session variable to keep track of how may posts are displayed</li>

  </ul></li>

 <li>Reset how many posts are displayed when the User logs out</li>

</ul>

<h2><a name="_Toc8588"></a>3.10           Objective 10: Liking Posts (and Displaying Like Count)</h2>

<ul>

 <li>Each post has a Like button and should display a Like Count (currently it always displays 0)</li>

 <li>Update the codebase to actually allows users to like posts and display a real like count</li>

 <li>Prevent users from double-liking a post (i.e each user can only like a post once)

  <ul>

   <li>HINT roughly copy how adding Friend Requests worked (i.e assigning id’s that correspond to which friend request was clicked, submitting AJAX POSTs with those id’s)</li>

   <li>DOUBLE HINT when returning posts in message_view, add an extra boolean attribute to each post object that let’s you know if the post has already been liked by the user</li>

   <li>TRIPLE HINT if a post has already been liked, set the button class to w3-disabled and remove the like-button class so the JQuery event no longer responds to it</li>

  </ul></li>

</ul>

<h2><a name="_Toc8589"></a>3.11           Objective 11: Create a Test Database</h2>

<ul>

 <li>Create a variety of test users, create many posts and likes and different friend requests to showcase all the functionality you’ve implemented</li>

 <li>Make sure to add and commit your db file and migrations folders so that the TA’s marking your assignment have access to the database you’ve populated</li>

</ul>

<h1><a name="_Toc8590"></a>4           README</h1>

You MUST document your code in a file CS1XA3/Project03/README.md

<ul>

 <li>The document should be styled with MarkDown (see <a href="https://guides.github.com/features/mastering-markdown/">https://guides.github.com/features/ </a><a href="https://guides.github.com/features/mastering-markdown/">mastering-markdown/</a><a href="https://guides.github.com/features/mastering-markdown/">)</a></li>

 <li>The document should describe usage of the server, locally and on mac1xa3, and how to log in with any TestUser you’ve set up</li>

 <li>The document should contain a section (header) for each objective that gives a description of how you implemented the objective and how you handled any exceptional use cases</li>

</ul>

An example of the general outline of the document would be as follows (this is not an exact template you need to follow, you are encouraged to use your best judgment for constructing a useful README):

# CS 1XA3 Project03 – &lt;MyMacId&gt;

## Usage

Install conda enivornment with …

…

Run locally with python manage.py runserver localhost:8000

Run on mac1xa3.ca with python manage.py runserver localhost:100192 …

Log in with TestUser, password SomePassword … ## Objective 01 Description:

<ul>

 <li>this feature is displayed in something.djhtml which is rendered by some_view</li>

 <li>it makes a POST Request to from something.js to /e/macid/something_post which is handled by someting_post_view Exceptions:</li>

 <li>If the /e/macid/something_post is called without arguments is redirects to login.djhtml</li>

</ul>

## Objective 02 …