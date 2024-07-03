# 0x00. Personal Data Resources

## Description
This project focuses on understanding and handling personal data. It covers the basics of Personally Identifiable Information (PII), logging practices, and password encryption. By the end of this project, you will be able to explain key concepts and implement solutions for managing and protecting personal data.

## Resources
Read or watch the following resources to build a foundational understanding:
- [What Is PII, non-PII, and Personal Data?](https://www.example.com/what-is-pii)
- [Logging Documentation](https://docs.python.org/3/howto/logging.html)
- [bcrypt Package](https://pypi.org/project/bcrypt/)
- [Logging to Files, Setting Levels, and Formatting](https://realpython.com/python-logging/)

## Learning Objectives
By the end of this project, you should be able to explain the following concepts without needing to refer to external sources:

1. **Examples of Personally Identifiable Information (PII)**
   - PII refers to any data that can be used to identify a specific individual. Examples include:
     - Full name
     - Social Security number
     - Email address
     - Phone number
     - Home address
     - Financial information

2. **How to Implement a Log Filter that Will Obfuscate PII Fields**
   - Logging is crucial for tracking application behavior and debugging issues. However, logging sensitive information like PII should be avoided. Implement a log filter to obfuscate PII fields in log messages.
   - Example using Python logging:
     ```python
     import logging
     import re

     class PiiFilter(logging.Filter):
         def filter(self, record):
             record.msg = re.sub(r'\b(\d{3}-\d{2}-\d{4})\b', '***-**-****', record.msg)  # Example for SSN
             return True

     logger = logging.getLogger('my_logger')
     logger.addFilter(PiiFilter())
     ```

3. **How to Encrypt a Password and Check the Validity of an Input Password**
   - Password encryption is essential for security. Use the bcrypt package to hash passwords and verify input passwords.
   - Example using bcrypt:
     ```python
     import bcrypt

     # Encrypt password
     password = b"super_secret_password"
     hashed = bcrypt.hashpw(password, bcrypt.gensalt())

     # Check password
     if bcrypt.checkpw(password, hashed):
         print("Password is valid!")
     else:
         print("Invalid password!")
     ```

4. **How to Authenticate to a Database Using Environment Variables**
   - Storing database credentials in environment variables is a best practice to enhance security.
   - Example using Python and environment variables:
     ```python
     import os
     import psycopg2

     # Set environment variables (usually done outside the script)
     os.environ['DB_USER'] = 'your_username'
     os.environ['DB_PASSWORD'] = 'your_password'

     # Retrieve environment variables
     db_user = os.getenv('DB_USER')
     db_password = os.getenv('DB_PASSWORD')

     # Connect to the database
     connection = psycopg2.connect(
         dbname='your_dbname',
         user=db_user,
         password=db_password,
         host='localhost'
     )
     ```

## Conclusion
This project aims to equip you with essential skills for handling personal data responsibly. Understanding PII, logging practices, password encryption, and secure database authentication are critical components in protecting sensitive information.

Happy learning!
