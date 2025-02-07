## College Sit3

Created new Drupal project uding Docker, ddev, composer and drush.

### Creating Content Types

If we want to add entities like student, teacher then we have to go to
`Manage > Structure > Content Types`
and then create the contents in below way
<pre>
Name: Teacher
Description: Content type for teacher profiles.
Click Save and Manage Fields.

    Add then add the fields:
        Text (Plain): Name (Label: Teacher Name)
        Image: Profile Picture (Label: Profile Image)
</pre>

Created 3 seperate entities in similar way

1. Teacher
    - Name
    - Profile Picture
    - Biography
    - Specialization
    - Office Hours
    - Social media links
    - Email

2. Student
    - Name
    - Profile Picture
    - Personal Statement
    - Course
    - Year of Study

3. Department
    - Dept Name
    - Dept Description
    - Faculty members *(FK to entity Teacher)*
---

### Creating Taxonomies

Now is time to create Taxonomies

go to
`Manage > Structure > Taxonomy`

To create new Taxonomy click on **Add Vocabulary** button.

Give it name save and terms in it.
like for Department - Engineering, Marketing ,etc.


### Adding Taxonomy Reference Fields to Content Types
Go to Content Type and add new field as 'reference > taxonomy'.
and select created taxonomy from Vocabulary.


### Time to setup permissions.
Go to `manage > people > permissions / roles`
and add permissions as per the requirenments.

### Creating new users

Go to https://first.ddev.site/node/add/student to add new student and so on................


---
---
---

That was it for project related info next part covers what else I learned during the process.




---
<center>

### 6 feb
</center>
<br>

In waterfall project added **taxonomy** for *location* and then changed field from `autocomplete` to `select list` to do so we have to go to **Manage form display**.

Added new difficulty taxonomy which will hold one media image for displaying the difficulty of waterfall for trekking.


In the list of that same taxonomy created 3 terms indicating <b> Easy, Medium </b> and **High** difficulty. <br>
In waterfall **conteny type** created new field to taxonomy reference to that Vocabulary.

Learned abot the extensions named

for the role **Content manager** changed some permissions giving it access to control the media and all the node permissions.

Who can register accounts --- Visitors. Email verificatio uncheck.


---

### What about a bot

- Extend - JSON:API installation.
- Create custom module
- install it.
- add that block on block layout
<center>

**abondaned**

</center>

---




### Exploring permissions

created custom roles for the same. <br>
gave permissions for student n teacher roles.<br>
added create account option for visitors.<br>
added role field in the create account form.<br>

**problem faced 1**
but they cannot access permissions. *solved* -> gave permission to access the content overview option...<br>
![content creation fix](image.png)

**problem faced 2**
Now the role is not properly being assigned to the user while registering from the website itself.
