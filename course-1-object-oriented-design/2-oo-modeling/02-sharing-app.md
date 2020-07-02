# Ungraded Assignment - UML Class Diagram for Sharing App

Produce a UML class diagram from a given code base for an item sharing application.

In its current state, a user of the app the owner is able to record the items they own and wish to share.

The owner may view all of their items, their ***Available*** items, or their ***Borrowed*** items.

The owner may change the status of an item they own from Available to Borrowed and back.

When an item’s status is changed to Borrowed, the owner must enter the username of the borrower.

Construct a UML class diagram that captures all the classes and relationships in the code base. For each class you should document all attributes and methods:
  - MainActivity
  - SectionsPagerAdapter
  - ItemsFragment
  - AllItemsFragment
  - AvailableItemsFragment
  - BorrowedItemsFragment
  - AddItemActivity
  - EditItemActivity
  - ItemList
  - Item
  - ItemAdapter
  - Dimensions

You should also include any superclasses that the above classes inherit from. However, you are NOT required to document any methods or variables from these, only their names:
  - AppCompatActivity
  - FragmentPagerAdapter
  - ArrayAdapter<Item>
  - Fragment

Style guidelines for UML class diagram:
  - Superclasses should be drawn above subclasses
  - Whole things should be drawn to the left of the part
  - There should be few crossing edges
  - Boxes should not overlap other boxes or edges
  - Diagram should flow from top to bottom and left to right

## Solution

You can view my solution from here [02-item-sharing-class-diagram.pdf](./02-item-sharing-class-diagram.pdf).
