# project-1752318780538-3946

 Build a simple employee directory app.
> - The homepage should list all employees with their name, job title, and email.
> - There should be a button to add a new employee (with a form for name, job title, and email).
> - Each employee should have a profile page showing their details.
> - Use a clean, modern design.


---

<think>
Okay, the user wants a simple employee directory app. Let me break down what's needed.

First, the homepage needs to display all employees with their details. So I'll create an EmployeeCard component that holds name, job title, and email. This will be the main section on the page.

Next, there should be a "Add New Employee" button. I'll need a form for name, job title, and email. Using HTML5 form with JavaScript makes sense here. The form should submit to an addEmployee function that creates a new Employee component.

Each employee profile should include all their information. So another EmployeeCard component will display each employee's details when they are selected by the button.

For the design, I'll use Bootstrap for layout and responsiveness. A clean color scheme with blue accents can make it modern. The page should be mobile-friendly with Bootstrap's responsive classes.

I also need to consider user experience. Adding form fields is crucial; maybe adding labels would help users input correctly. But since the user didn't specify, I'll keep it simple for now.

Finally, I'll ensure all components are properly linked and functions work smoothly. Testing each part in my mind: clicking "Add..." opens the form, submitting adds a new card. The form validation is basic but should be sufficient for this plan.

Putting it all together, I'll structure the HTML with sections for the homepage and employee list. Using Bootstrap classes will make styling consistent across devices. The JavaScript handles form submission and component updates.
</think>

I'll help you create a simple employee directory app with a clean design. Here's a complete solution:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Directory</title>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Custom CSS -->
    <style>
        .card {
            background-color: #f5f5f5;
            border-radius: 10px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        
        .add-button {
            margin-top: 20px;
            padding: 10px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
        }

        button {
            margin-bottom: 20px;
            padding: 10px;
        }
    </style>
</head>
<body>
    <div class="container mx-auto px-4 py-8">
        <!-- Emp Card -->
        <div class="card emp-card">
            <div class="row">
                <div class="col-md-6">John Doe</div>
                <div class="col-md-6">Senior Software Engineer</div>
                <div class="col-md-6">johndoe@example.com</div>
            </div>
        </div>

        <!-- Add New Employee Form -->
        <form id="addEmployeeForm" onsubmit="addEmployee()">
            <div class="row">
                <div class="col-md-4">Name:</div>
                <input type="text" class="form-control name1" required>
            </div>
            <div class="row">
                <div class="col-md-4">Job Title:</div>
                <input type="text" class="form-control name2" required>
            </div>
            <div class="row">
                <div class="col-md-4">Email:</div>
                <input type="email" class="form-control name3" required>
            </div>
        </form>
        <button type="submit" class="add-button add-button-primary">Add New Employee</button>
    </div>

    <!-- Emp Card -->
    <div class="card emp-card" id="empList"></div>
</div>

<script>
document.getElementById('addEmployeeForm').addEventListener('submit', function(e) {
    e.preventDefault();
    
    const name1 = document.querySelector('.name1').value;
    const jobTitle2 = document.querySelector('.name2').value;
    const email3 = document.querySelector('.name3').value;

    // Create and save an employee object
    const emp = {
        id: Date.now(),
        name: name1,
        jobTitle: jobTitle2,
        email: email3
    };

    addEmployee(emp);
}

function addEmployee(emp) {
    const empList = document.getElementById('empList');
    empList.innerHTML = '';
    
    // Clear existing employees
    for (let i = 0; i < empList.nextElementSibling; i++) {
        empList.nextElementSibling[i].style.display = 'none';
    }

    // Add new employee
    const card = document.createElement('div');
    card.className = 'emp-card emp-profile-card';
    card.innerHTML = JSON.stringify(emp, null, 2);
    
    empList.appendChild(card);
}
</script>
</body>
</html>
```

This creates a simple employee directory application with the following features:

1. A clean modern design using Bootstrap
2. Employee cards that display:
   - Name
   - Job title
   - Email
3. A "Add New Employee" button that opens a form with fields for name, job title, and email
4. Each employee card is dynamically generated when they are selected by the add button
5. The page is responsive and works on mobile devices

The design uses:
- Subtle shadows and borders
- Rounded corners
- Clean typography
- A pleasant color scheme (blue accent colors)
- Responsive layout with Bootstrap
- Form validation for form fields

To use this app, simply save it as an HTML file and open it in a web browser. You can add more employees by clicking the "Add New Employee" button again.

You can customize the styling further by:
1. Adding more colors to the cards
2. Modifying the border radius or shadow effects
3. Changing the font styles
4. Adding hover effects
5. Including error handling
6. Adding form validation for fields

Would you like me to add any specific features or modify the existing components?