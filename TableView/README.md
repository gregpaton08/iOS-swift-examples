# Table View Example

## Starting From a Blank Project

### Update the Storyboard

1. In Main.storyboard delete the existing view controller.
2. Drag out a Table View Controller.
    * Optionally, drag out a navigation view controller which will include a table view controller.

### Create a Custom Subclass of UITableViewController

1. Add a new file of type Cocoa Touch Class. Set the "Subclass of:" to be UITableViewController and give the file a name (TableViewController.swift in this example).
2. In Main.storyboard go to the Identity Inspector for the Table View Controller and set the "Class" under "Custom Class" to be the new subclass of UITableViewController that you just created (TableViewController in this example).

### Implement the UITableViewDataSource Methods

1. Optionally implement the numberOfSections method to return the number of sections (this should correspond to your data model). If not implemented the method returns 1 by default.
2. Implement the numberOfRowsInSection method to return the number of rows for that section (this should correspond to your data model).
3. Implement the cellForRowAt method to configure the cell for a given index path.
   * Call the dequeueReusableCell method off of your view controllers table view var. This method returns a UITableViewCell from a pool.
   * This method requires you to provide a reuse identifier. Choose a unique string (in this case "reuseIdentifier").
   * In Main.storyboard select the prototype cell's attribute inspector and set the "Identifier" to the string you chose above (in this case "reuseIdentifier").

### Create a Custom Subclass of UITableViewCell (optional)

Optionally create a custom subclass of UITableViewCell if you require more functionality than the default class provides. 

1. Add a new file of type Cocoa Touch Class. Set the "Subclass of:" to be UITableViewCell and give the file a name (TableViewCell.swift in this example).
2. In Main.storyboard go to the Identity Inspector for the prototype cell inside the table view. Set the "Class" under "Custom Class" to be the new subclass of UITableViewCell that you just created (TableViewCell in this example).
3. Add optional views in the new custom cell (buttons, switches, etc.) and wire them to the new class.
4. To access the cell cast it as the custom class in the cellForRowAt method in your table view controller.
    ```
    if let cell = tableView.dequeueReusableCell(withIdentifier: "reuseIdentifier", for: indexPath) as? TableViewCell {
        
        // Configure the cell...
        
        return cell
    }
    ```