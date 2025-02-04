
### **1. Set Up Content Types**

The steps for creating content types (for Teachers, Students, and Departments) are the same in **Drupal 11**.

#### **A. Create Custom Content Types for Teacher, Student, and Department**
1. **Go to Content Types**:
   - Navigate to `https://first.ddev.site/admin/structure/types`
   - Click **Add content type**.

2. **Create Teacher Content Type**:
   - **Name**: `Teacher`
   - **Description**: Content type for teacher profiles.
   - Click **Save and Manage Fields**.
     - Add the following fields:
       - **Text (Plain)**: `Name` (Label: Teacher Name)
       - **Image**: `Profile Picture` (Label: Profile Image)
       - **Text (Long)**: `Biography` (Label: Biography)
       - **Text (Plain)**: `Specialization` (Label: Subject Specialization)
       - **Text (Plain)**: `Office Hours` (Label: Office Hours)
       - **Link**: `Social Media` (Label: Social Media Links)
       - **Text (Plain)**: `Email` (Label: Email)

3. **Create Student Content Type**:
   - **Name**: `Student`
   - **Description**: Content type for student profiles.
   - Click **Save and Manage Fields**.
     - Add fields like:
       - **Text (Plain)**: `Name` (Label: Student Name)
       - **Image**: `Profile Picture` (Label: Profile Image)
       - **Text (Long)**: `Personal Statement` (Label: Personal Statement)
       - **Text (Plain)**: `Course` (Label: Course/Program)
       - **Text (Plain)**: `Year of Study` (Label: Year of Study)

4. **Create Department Content Type**:
   - **Name**: `Department`
   - **Description**: Content type for department pages.
   - Click **Save and Manage Fields**.
     - Add fields like:
       - **Text (Plain)**: `Department Name` (Label: Department Name)
       - **Text (Long)**: `Department Description` (Label: Department Description)
       - **Entity Reference**: `Faculty Members` (Label: Teachers in Department) – Reference Teacher profiles.

5. **Create Landing Page (Basic Page)**:
   - You can use the default **Basic Page** content type or create a custom one.
   - Add fields like:
     - **Text (Long)**: `Main Content` (For site introduction, CTA buttons, etc.)
     - **Image**: Hero image or banner.

---

### **2. Set Up Taxonomies**

Taxonomies are essential for organizing your content by categories like departments and courses. In **Drupal 11**, the process remains the same as in earlier versions.

#### **A. Create Department Taxonomy**
1. Navigate to: `https://first.ddev.site/admin/structure/taxonomy`.
2. Click **Add vocabulary**.
   - **Name**: `Department`
   - Add terms like **Math**, **Science**, **Engineering**, etc.

#### **B. Create Course Taxonomy (Optional)**
1. Navigate to: `https://first.ddev.site/admin/structure/taxonomy`.
2. Click **Add vocabulary**.
   - **Name**: `Courses`
   - Add terms like **Computer Science**, **Physics**, **Mathematics**, etc.

#### **C. Add Taxonomy Reference Fields to Content Types**
- Go to each content type you created (Teacher, Student, Department).
- **For Teacher** and **Student** content types:
  1. **Go to Manage Fields**.
  2. Add a **taxonomy reference field** for **Department**.
  3. Optionally add a **taxonomy reference field** for **Courses** for the **Student** content type.

---

### **3. Set Up Permissions**

Permissions control who can create, view, and edit the various content types. **Drupal 11** still uses the same permission system.

#### **A. Set Permissions for Roles**
1. Navigate to: `https://first.ddev.site/admin/people/permissions`
2. For each role (`Authenticated User`, `Teacher`, `Student`, `Administrator`), configure the permissions:
   - **Teacher Role**: Allow creating/editing their **Teacher Profile**.
   - **Student Role**: Allow viewing student and teacher profiles (and possibly editing their own student profile).
   - **Administrator Role**: Allow full access to create/edit all content.

#### **B. Create Custom Roles (Optional)**
- You can create a custom role (e.g., `Teacher` or `Student`) under `https://first.ddev.site/admin/people/roles` and assign the correct permissions.

---

### **4. Create Content for Teachers, Students, and Departments**

#### **A. Create Teacher Profiles**
1. Navigate to: `https://first.ddev.site/node/add/teacher`
2. Fill in the fields with appropriate teacher information (Name, Bio, Subject Specialization, etc.).
3. Assign the **Department taxonomy** term (e.g., Science, Engineering).
4. Save the Teacher profile.

#### **B. Create Student Profiles**
1. Navigate to: `https://first.ddev.site/node/add/student`
2. Fill in the student profile fields (Name, Course, Year of Study).
3. Assign the **Department** and optionally **Course** taxonomy terms.
4. Save the Student profile.

#### **C. Create Department Pages**
1. Navigate to: `https://first.ddev.site/node/add/department`
2. Fill in the department name, description, and reference the **Teachers** associated with that department.
3. Save the Department page.

#### **D. Create the Landing Page**
1. Navigate to: `https://first.ddev.site/node/add/basic-page`
2. Add content (text, images, CTA buttons) for the landing page.
3. Save the page.

---

### **5. Create Views to Display Lists of Teachers, Students, and Departments**

In **Drupal 11**, the process for creating Views is largely the same.

1. **Create View for Teachers**:
   - Navigate to: `https://first.ddev.site/admin/structure/views`
   - Click **Add view**.
   - **View name**: `Teachers List`
   - **Show**: Content of type **Teacher**
   - Add filters like **Department** and **Specialization**.
   - Add fields like **Name**, **Profile Image**, and **Bio**.
   - Save the view.

2. **Create View for Students**:
   - Follow the same process for **Student Profiles**, adding fields for **Name**, **Course**, **Year of Study**, etc.

3. **Create View for Departments**:
   - Follow the same process for **Department Pages**, displaying **Department Name** and a list of **Teachers** associated with the department.

---

### **6. Set Up Navigation**

1. **Add Menus**:
   - Navigate to `https://first.ddev.site/admin/structure/menu`.
   - Add a new menu, for example, `Main Menu`.
   - Add links to the Landing Page, Teachers List, Students List, and Departments.

2. **Update Blocks**:
   - Go to `https://first.ddev.site/admin/structure/block` to place the views (Teachers List, Students List, Departments List) as blocks in various regions of your site (e.g., sidebar, footer, etc.).

---

### **Final Notes**:
- **Drupal 11 themes** like **Olivero** and **Bartik** are responsive out of the box, so you don't need to worry much about making your site mobile-friendly.
- If you haven’t chosen a theme yet, you can easily switch to **Olivero** or use a theme like **Radix** (if you want a Bootstrap-based layout).
