Feature: Searching and purchasing a book in a favorite online bookstore

Background:
  Input data:
    | User      | Email Address     | Password |
    | John      | john@example.com  | password |

  Scenario: User logs in to their account
    Given the user opens the login page
    When the user enters their login details
    And the user clicks the "Log In" button

  Scenario: Searching and purchasing a book
    Given the user searches for a book
    When the user enters "Fantastic Beasts" in the search bar
    And the user clicks the "Search" button

    When the user selects a book to purchase
    Then the user adds the book to the cart

    When the user completes the purchase
    Then the user proceeds to the cart
    And the user checks the cart contents
    And the user clicks the "Proceed to Payment" button
    And the user enters shipping and payment information
    And the user clicks the "Place Order" button

  Scenario: Purchase validation
    When the user checks the order confirmation
    Then the user receives an email confirming the purchase
    And the user verifies that the order number is correct
    And the user verifies that the book is mentioned in the confirmation email

    When the user checks the delivery status
    Then the user receives information about the delivery status
    And the user confirms that the book is on its way