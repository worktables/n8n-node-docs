# n8n-node-docs

Here's the complete documentation for your n8n custom node:

---

# **Monday.com API Integration Node (n8n Custom Node)**

This custom node integrates with the Monday.com API to fetch data from a specified board. It retrieves the list of items from the board based on the `boardId` provided and allows you to display a list of items to select from. This node is ideal for automating tasks related to Monday.com, such as fetching items from specific boards and performing further actions based on selected items.

---

## **Parameters**

### 1. **Board ID (boardId)**  
   - **Type**: String (Required)  
   - **Description**: The ID of the Monday.com board from which you want to fetch items. This ID is essential for identifying the board in the Monday.com API.  
   - **Example**: `123456789`

### 2. **API Token (apiToken)**  
   - **Type**: String (Required)  
   - **Description**: The Monday.com API token that provides authentication for accessing your Monday.com account. You can generate an API token from your Monday.com account settings.  
   - **Example**: `your_api_token_here`

### 3. **Columns to Retrieve (columns)**  
   - **Type**: Array of Strings (Optional)  
   - **Description**: A list of column names you want to retrieve for each item. If not provided, the node will retrieve all available columns.  
   - **Example**: `["name", "status", "due_date"]`

### 4. **Item ID (itemId)**  
   - **Type**: String (Optional)  
   - **Description**: The ID of a specific item you want to retrieve from the board. If left blank, the node will retrieve all items from the specified board.  
   - **Example**: `987654321`

---

## **Usage Examples**

### **Example 1: Retrieve All Items from a Board**

This example demonstrates how to retrieve all items from a specific Monday.com board by providing the `boardId` and `apiToken`.

1. **Input Parameters**:
   - `boardId`: `123456789`
   - `apiToken`: `your_api_token_here`
   
2. **Output**:
   - A list of all items from the specified board.

---

### **Example 2: Retrieve Specific Columns for Items**

In this example, you can specify the columns you wish to retrieve for each item.

1. **Input Parameters**:
   - `boardId`: `123456789`
   - `apiToken`: `your_api_token_here`
   - `columns`: `["name", "status", "due_date"]`

2. **Output**:
   - A list of items with only the specified columns (`name`, `status`, `due_date`).

---

### **Example 3: Retrieve a Specific Item**

If you need to retrieve a single item from a board, you can provide the `itemId` for that item.

1. **Input Parameters**:
   - `boardId`: `123456789`
   - `apiToken`: `your_api_token_here`
   - `itemId`: `987654321`

2. **Output**:
   - The data for the specific item with the provided `itemId`.

---

## **Error Handling**

Below are some common errors you may encounter when using the Monday.com API integration node:

### 1. **Invalid API Token**
   - **Error Message**: `Invalid API token provided.`
   - **Solution**: Ensure that you are using a valid API token from your Monday.com account. Check the token in your account settings and re-enter it.

### 2. **Invalid Board ID**
   - **Error Message**: `Invalid board ID provided.`
   - **Solution**: Verify the `boardId` you are using. You can find this ID by accessing the board's settings or using the Monday.com API to list your boards.

### 3. **Network/Connection Errors**
   - **Error Message**: `Unable to connect to Monday.com API.`
   - **Solution**: Ensure that your internet connection is stable. If the issue persists, check Monday.com’s API status for any outages.

---

## **Node Configuration and Setup**

### **Step-by-step Configuration**

1. **Install the Node in n8n**  
   - Go to n8n and navigate to the `Node Settings` in the left sidebar.
   - Create a new node by pasting the code for this custom node.
   - In the configuration page, ensure that you provide the `boardId` and `apiToken` for proper authentication.

2. **Provide Parameters**  
   - Enter the **Board ID** from which you wish to fetch items.
   - Enter your **API Token** from Monday.com to authenticate requests.
   - Optionally, enter specific **columns** you want to retrieve for each item.
   - Optionally, provide an **Item ID** if you want to fetch a single item from the board.

3. **Test the Node**  
   - Run the workflow after configuring the node to ensure it's correctly fetching data from your Monday.com board.

---

## **Additional Notes**

- This node is designed to work with the Monday.com API. Ensure you have API access and a valid token.
- The node returns data in JSON format, which can be used in subsequent steps in your n8n workflows for further processing.
- If you are using multiple boards or need to perform different operations, you can create multiple instances of this node, each with different configurations.
