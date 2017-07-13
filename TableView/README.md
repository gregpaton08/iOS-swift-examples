# Table View Example

## Starting From a Blank Project

1. In Main.storyboard delete the existing view controller. Then, drag out a Table View Controller. Optionally, place this inside a navigation view controller.
2. Add a new file of type Cocoa Touch Class. Set the "Subclass of:" to be UITableViewController (TableViewController.swift in this example).
3. In Main.storyboard go to the Identity Inspector for the Table View Controller and set the "Class" under "Custom Class" to be the new subclass of UITableViewController that you just created (TableViewController in this example).