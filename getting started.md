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
