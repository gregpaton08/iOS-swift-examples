# Table View Example

## Starting From a Blank Project

### Update the Storyboard

1. In Main.storyboard delete the existing view controller.
2. Drag out a Table View Controller.
  * Optionally, drag out a navigation view controller which will include a table view controller.

### Create a Custom Subclass of UITableViewController

1. Add a new file of type Cocoa Touch Class. Set the "Subclass of:" to be UITableViewController (TableViewController.swift in this example).
2. In Main.storyboard go to the Identity Inspector for the Table View Controller and set the "Class" under "Custom Class" to be the new subclass of UITableViewController that you just created (TableViewController in this example).

### Implement the UITableViewDataSource Methods

1. Optionally implement the numberOfSections method to return the number of sections (this should correspond to your data model). If not implemented the method returns 1 by default.
2. Implement the numberOfRowsInSection method to return the number of rows for that section (this should correspond to your data model).
3. Implement the cellForRowAt method to configure the cell for a given index path.
   * Call the dequeueReusableCell method off of your view controllers table view var. This method returns a UITableViewCell from a pool.
   * This method requires you to provide a reuse identifier. Choose a unique string (in this case "reuseIdentifier").
   * In Main.storyboard select the prototype cell's attribute inspector and set the "Identifier" to the string you chose above (in this case "reuseIdentifier").