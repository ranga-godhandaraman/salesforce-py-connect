# salesforce-py-connect

## Salesforce Integration Script

This script demonstrates how to connect to Salesforce using the `simple_salesforce` Python library and query Account records. It provides an example of authentication and executing a SOQL query to retrieve and print Account information.

### Prerequisites

- Python 3.x installed on your machine
- Salesforce account with appropriate API access
- Salesforce connected app credentials (consumer key and consumer secret)

### Installation

1. First, ensure you have `pip` installed. You can install the `simple_salesforce` library using the following command:

    ```bash
    pip install simple_salesforce
    ```

### Setup

Before running the script, you need to gather your Salesforce credentials:

- `username`: Your Salesforce username
- `password`: Your Salesforce password
- `consumer_key`: The consumer key of your connected app in Salesforce
- `consumer_secret`: The consumer secret of your connected app in Salesforce

### Script Explanation

The script performs the following tasks:

1. **Imports the `Salesforce` class from the `simple_salesforce` library.**

    ```python
    from simple_salesforce import Salesforce
    ```

2. **Establishes a connection to Salesforce using the provided credentials.**

    ```python
    sf = Salesforce(username='your_username', password='your_password', consumer_key='your_consumer_key', consumer_secret='your_consumer_secret')
    ```

3. **Executes a SOQL query to retrieve the first five Account records.**

    ```python
    query_result = sf.query('SELECT Id, Name FROM Account LIMIT 5')
    ```

4. **Iterates over the query results and prints the Account ID and Name.**

    ```python
    for record in query_result['records']:
        print(f"Account ID: {record['Id']}, Name: {record['Name']}")
    ```

### Usage

1. Replace the placeholder values in the script with your actual Salesforce credentials:

    ```python
    sf = Salesforce(username='your_username', password='your_password', consumer_key='your_consumer_key', consumer_secret='your_consumer_secret')
    ```

2. Run the script:

    ```bash
    python your_script_name.py
    ```

3. The script will output the Account IDs and Names of the first five accounts found in your Salesforce instance.

### Example Output

```
Account ID: 001xx000003DHPaAAO, Name: Acme Corporation
Account ID: 001xx000003DHPbAAO, Name: Global Media
Account ID: 001xx000003DHPcAAO, Name: Tech Innovators
Account ID: 001xx000003DHPdAAO, Name: Quick Supplies
Account ID: 001xx000003DHPeAAO, Name: Smart Solutions
```

### Notes

- Ensure your Salesforce connected app has API access enabled and the necessary OAuth scopes.
- Keep your credentials secure and do not hardcode them in production scripts. Consider using environment variables or secure credential storage mechanisms.

### Troubleshooting

- If you encounter authentication issues, double-check your username, password, consumer key, and consumer secret.
- Ensure your Salesforce account has the appropriate permissions to access the API and the objects you're querying.

### Additional Resources

- [Simple Salesforce Documentation](https://pypi.org/project/simple-salesforce/)
- [Salesforce SOQL Documentation](https://developer.salesforce.com/docs/atlas.en-us.soql_sosl.meta/soql_sosl/)
- [GitHub Docs for Simple SalesForce](https://github.com/simple-salesforce/simple-salesforce/)
