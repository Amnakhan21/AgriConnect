# AgriConnect
A Python-based platform connecting farmers and buyers
### 🌾 Farmer Product Flow
Below is the logic for how a Farmer adds a product to the AgriConnect platform:

```mermaid
graph TD
    Start([Farmer Logs In]) --> Dash[Farmer Dashboard]
    Dash -->|Click 'Add New Produce'| Form[Open Product Form]
    Form --> Input[Input: Name, Qty, Price]
    Input --> Submit{Submit?}
    Submit -->|Yes| Auth[Flask API: Validate JWT]
    Auth -->|Valid| DB[(MongoDB: Save Product)]
    DB --> Notify[Success Alert]
    Notify --> Update[Update Dashboard Table]
    Update --> End([Product Live])
