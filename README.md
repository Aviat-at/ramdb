ramdb
ramdb is a lightweight, in-memory database built using Python's memory-mapped file capabilities. It simulates a simple database system by loading data (e.g., from MySQL) into RAM, enabling rapid query responses and benchmarking comparisons between traditional MySQL queries and in-memory queries.

Features
In-Memory Data Storage: Utilizes a memory-mapped file to simulate a RAM database.
MySQL Integration: Load data directly from MySQL tables (e.g., the departments table from an employees database) into RAM.
Fast Query Execution: Offers a query engine that performs bit-address based lookups for fast data retrieval.
Performance Benchmarking: Compare query execution times between MySQL and ramdb.
Debug and Testing Tools: Includes scripts for testing MySQL connections, loading data, and debugging RAM storage.
Swap System: Contains a simple mechanism to move data from RAM to disk (SSD) when memory is limited.
File Overview
benchmark_ram_vs_mysql.py: Benchmarks and compares the query performance of MySQL versus the in-memory ramdb.
test_mysql_loader.py: Loads the departments table from MySQL into ramdb and prints all stored records for verification.
query_engine.py: Provides methods for inserting and fetching records using bit-address lookup.
memory_manager.py: Manages the low-level memory mapping, including allocation and fetching of records.
debug_ram_storage.py: Debug utility that reloads data into ramdb and prints stored records for troubleshooting.
mysql_loader.py: Connects to a MySQL database and loads selected table data into the in-memory ramdb.
test_mysql_connection.py: Verifies the connection to the MySQL database and lists available tables.
swap_system.py: Implements a basic swap mechanism to offload records from RAM to disk when needed.
Installation
Prerequisites
Python 3.6 or higher
MySQL Server
Python packages:
mysql-connector-python
Setup Steps
Clone the Repository:

bash
Copy
git clone https://github.com/yourusername/ramdb.git
cd ramdb
Create and Activate a Virtual Environment (Optional but Recommended):

bash
Copy
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install Dependencies:

bash
Copy
pip install mysql-connector-python
Configure MySQL Connection:

Update the MySQL configuration details (host, user, password, database) in the following files as needed:
benchmark_ram_vs_mysql.py
test_mysql_loader.py
test_mysql_connection.py
mysql_loader.py
Make sure your MySQL server is running and accessible.

Usage
Loading Data into ramdb
You can load data from a MySQL table into ramdb using the mysql_loader.py script. For example, run the following script to load the departments table:

bash
Copy
python test_mysql_loader.py
Running Benchmarks
To compare the query performance between MySQL and ramdb, run:

bash
Copy
python benchmark_ram_vs_mysql.py
The script executes a test query on both systems and prints the execution time in microseconds.

Debugging and Testing
Debug RAM Storage: Use debug_ram_storage.py to inspect the contents of ramdb after loading data.

bash
Copy
python debug_ram_storage.py
Test MySQL Connection: Verify your MySQL connection with:

bash
Copy
python test_mysql_connection.py
Contributing
Contributions to ramdb are welcome! To contribute:

Fork the repository.
Create a feature branch (git checkout -b feature/YourFeature).
Commit your changes (git commit -am 'Add new feature').
Push to the branch (git push origin feature/YourFeature).
Create a new Pull Request.
License
This project is open source and available under the MIT License.

Acknowledgements
Built using Python's built-in libraries such as mmap and pickle.
Inspired by the need for fast, in-memory data processing and simple integration with traditional databases.
