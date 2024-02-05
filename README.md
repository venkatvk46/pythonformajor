# generate_employee_data.py
import random

# Sample data for employee names, cities, and phone numbers
employee_names = ['John Doe', 'Jane Smith', 'Michael Johnson', 'Emily Davis', 'James Brown']
cities = ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']
phone_numbers = ['123-456-7890', '234-567-8901', '345-678-9012', '456-789-0123', '567-890-1234']

# Generate 100 employees with random data
employees = []
for i in range(100):
    name = random.choice(employee_names)
    city = random.choice(cities)
    phone_number = random.choice(phone_numbers)
    employees.append((name, city, phone_number))

# Write the HTML content
html_content = """
<!DOCTYPE html>
<html>
<head>
    <title>Employee Data</title>
    <style>
        table {
            border-collapse: collapse;
            width: 100%;
        }
        th, td {
            border: 2px solid black;
            padding: 8px;
            text-align: left;
        }
    </style>
</head>
<body>
    <h2>Employee Data</h2>
    <table>
        <tr>
            <th>Name</th>
            <th>City</th>
            <th>Phone Number</th>
        </tr>
"""

# Populate table rows with employee data
for employee in employees:
    html_content += f"""
        <tr>
            <td>{employee[0]}</td>
            <td>{employee[1]}</td>
            <td>{employee[2]}</td>
        </tr>
    """

# Close the HTML content
html_content += """
    </table>
</body>
</html>
"""

# Write the HTML content to a file
with open('employee_data.html', 'w') as file:
    file.write(html_content)

print("HTML file generated successfully!")
