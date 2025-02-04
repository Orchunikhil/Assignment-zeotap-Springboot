Rule Engine with AST

Overview

This project is a simple 3-tier rule engine application that determines user eligibility based on attributes such as age, department, income, and spend. The system uses an Abstract Syntax Tree (AST) to represent conditional rules, allowing for dynamic creation, combination, and modification of these rules. The application includes a simple UI, API, and backend data storage using MongoDB.

Features

Define and store conditional rules as AST.
Combine multiple rules efficiently.
Evaluate rules against user data.
CRUD operations for rules.
Simple UI for creating and viewing rules.

Architecture
Frontend: HTML, JavaScript
Backend: Spring Boot
Database: MongoDB

Getting Started

Prerequisites
Java 8 or higher
Maven
MongoDB

Installation

Clone the repository:
sh
Copy
git clone https://github.com/yourusername/rule-engine-ast.git
cd rule-engine-ast

Set up MongoDB:
Ensure MongoDB is installed and running.
Create a database named ruleengine.
Configure application.properties: Modify src/main/resources/application.properties to match your MongoDB setup:

properties

Copy
spring.data.mongodb.uri=mongodb://localhost:27017/ruleengine
Build and run the application:
sh
Copy
mvn clean install
mvn spring-boot:run

Open the application:

Navigate to http://localhost:8080 in your web browser.

Usage
Creating a Rule
Open the application.

Enter a rule string in the input field (e.g., ((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)).

Click the "Create" button.

Viewing All Rules
The home page displays a list of all existing rules.

Evaluating Rules
Implement the evaluate_rule function to check a user's eligibility based on the defined rules.

API Endpoints

GET /: Home page, displays the form and list of rules.
POST /api/rules/create: Creates a new rule.
Request Body: { "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)" }
GET /api/rules/all: Retrieves all rules.
GET /api/rules/{id}: Retrieves a rule by ID.
DELETE /api/rules/{id}: Deletes a rule by ID.

Example Data

Sample MongoDB data for 10 objects:

json

Copy
[
  {
    "id": 1,
    "description": "Senior Software Engineer with expertise in full-stack development.",
    "experience": 8,
    "profile": "John Doe",
    "techs": ["Java", "Spring Boot", "React", "AWS"]
  },
  {
    "id": 2,
    "description": "DevOps Engineer with a passion for automation and infrastructure management.",
    "experience": 6,
    "profile": "Jane Smith",
    "techs": ["Docker", "Kubernetes", "Ansible", "Azure"]
  },
  {
    "id": 3,
    "description": "Data Scientist specializing in machine learning and big data analytics.",
    "experience": 5,
    "profile": "Emily Johnson",
    "techs": ["Python", "TensorFlow", "Spark", "Hadoop"]
  },
  {
    "id": 4,
    "description": "Backend Developer focused on microservices and cloud-native applications.",
    "experience": 7,
    "profile": "Michael Brown",
    "techs": ["Node.js", "Express", "MongoDB", "AWS Lambda"]
  },
  {
    "id": 5,
    "description": "Frontend Developer with a keen eye for design and user experience.",
    "experience": 4,
    "profile": "Jessica Williams",
    "techs": ["JavaScript", "Vue.js", "HTML", "CSS"]
  },
  {
    "id": 6,
    "description": "Mobile App Developer with a background in iOS and Android development.",
    "experience": 6,
    "profile": "David Miller",
    "techs": ["Swift", "Kotlin", "React Native", "Firebase"]
  },
  {
    "id": 7,
    "description": "Cloud Architect specializing in designing scalable cloud solutions.",
    "experience": 9,
    "profile": "Sophia Davis",
    "techs": ["AWS", "Terraform", "Python", "Azure"]
  },
  {
    "id": 8,
    "description": "Full Stack Developer with experience in building modern web applications.",
    "experience": 5,
    "profile": "James Wilson",
    "techs": ["JavaScript", "Angular", "Node.js", "MongoDB"]
  },
  {
    "id": 9,
    "description": "Security Engineer focused on securing applications and infrastructure.",
    "experience": 7,
    "profile": "Olivia Martinez",
    "techs": ["Penetration Testing", "SIEM", "Firewalls", "Cryptography"]
  },
  {
    "id": 10,
    "description": "AI/ML Engineer with expertise in building intelligent systems.",
    "experience": 6,
    "profile": "Daniel Anderson",
    "techs": ["Python", "PyTorch", "Natural Language Processing", "Computer Vision"]
  }
]
Contributing
Contributions are welcome! Please open an issue or submit a pull request with any improvements or fixes.

License
This project is licensed under the MIT License - see the LICENSE file for details.
