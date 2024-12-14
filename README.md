# SwiftUI People List and News App

This project showcases a SwiftUI application with two core functionalities:

1. **Displaying a list of people** with detailed views.
2. **Fetching and displaying news articles** from the NewsAPI.

---

## Features

### 1. People List and Details
- **People List**: Displays a list of individuals from a local JSON file (`json_example.json`).
- **Detail View**: Provides detailed information about each person, including their name, gender, age, address, and phone numbers.

### 2. News Integration
- **NewsAPI Integration**: Fetches the latest news articles about a specific topic (e.g., Tesla).
- **Error Handling**: Manages API errors and decoding issues with clear error messages.
- **Loading Indicator**: Displays a loading spinner while fetching articles.

---

## Project Structure

### SwiftUI Views
1. **`ContentView.swift`**:
   - Displays the list of people.
   - Allows navigation to a detailed view for a selected person.

2. **`DetailView.swift`**:
   - Presents detailed information about the selected person, including their address and phone numbers.

### Models
1. **`Person`**:
   - Represents a person with properties such as `firstName`, `surname`, `gender`, `age`, `address`, and `phoneNumbers`.
   - Loads data from the bundled JSON file using an extension on `Bundle`.

2. **`Address`**:
   - Represents the address of a person, including fields like `streetAddress`, `city`, `state`, and `postalCode`.

3. **`PhoneNumber`**:
   - Represents a phone number with a `type` (e.g., mobile, home) and `number`.

4. **`Article`**:
   - Represents a news article fetched from the NewsAPI, including properties like `title`, `author`, `source`, and `publishedAt`.

5. **`NewsResponse`**:
   - Represents the API response, which contains an array of articles and metadata.

### ViewModel
- **`ArticleViewModel`**:
   - Handles the fetching of articles from the NewsAPI.
   - Manages the app's state for articles, loading status, and errors.

---

## Setup Instructions

### Prerequisites
- **Xcode 14 or later**.
- A valid NewsAPI key (get one from [NewsAPI](https://newsapi.org/)).

### Steps to Run
1. Clone this repository:
   ```bash
   git clone <repository-url>
   ```

2. Add the `json_example.json` file to your project. Example structure:
   ```json
   [
       {
           "firstName": "Jane",
           "surname": "Doe",
           "gender": "Female",
           "age": 28,
           "address": {
               "streetAddress": "456 Maple Avenue",
               "city": "Anywhere",
               "state": "NY",
               "postalCode": "10001"
           },
           "phoneNumbers": [
               {"type": "Mobile", "number": "555-123-4567"},
               {"type": "Home", "number": "555-987-6543"}
           ]
       }
   ]
   ```

3. Replace the API key in `ArticleViewModel.swift`:
   ```swift
   private let apiKey = "your-api-key-here"
   ```

4. Build and run the project in Xcode.

---

## Usage

### People List
- Launch the app to see a list of people.
- Tap on a person to view detailed information.

### News Articles (Optional)
- Use the `ArticleViewModel` to create a new SwiftUI view for displaying articles.
- Ensure you have an active internet connection and a valid API key.

---

## Example Output

### People List
- **List View**:
  - Displays the names of people (e.g., Jane Doe).
- **Detail View**:
  - Shows detailed information like:
    - Name: Jane Doe
    - Gender: Female
    - Age: 28
    - Address: 456 Maple Avenue, Anywhere, NY 10001
    - Phone Numbers: Mobile: 555-123-4567, Home: 555-987-6543

### News Articles
- Displays the latest articles about Tesla (if implemented).

---

## Troubleshooting

- **Crash on Startup**:
  - Ensure `json_example.json` is added to the project bundle.
- **Invalid API Key**:
  - Verify your NewsAPI key is correct and active.
- **JSON Decoding Errors**:
  - Check that the JSON structure matches the expected format.

---

