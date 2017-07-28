Photowall Back End Developer Challenge
======================================
In this task you will create a simple shopping cart in PHP and test it with PHPUnit.

Installation
------------
Install the project and all dependencies
`$ composer update`

Run tests
`$ vendor/bin/phpunit`

Rules
-----
* You can only use the libraries that comes with the project
* You are allowed to rewrite or add new classes to the project if you need to. In fact you probably have to do this to complete the challenge in a good way.

Tasks
-----
Your task is to implement all use-cases in the list below. For each case you need to write at least one unit-test. We have provided you with
some sample code to help explain how the code should work however these are just examples and you do not need to follow them strictly.

*Task 1 - Add products to the cart*

It should be possible to create products and add them to the cart. The addItem method should take two arguments, product and quantity.
The quantity parameter should be optional and default to 1.

```
$cart = new Cart();
$apple = new Product(1, "Apple", 5);
$cart->addItem($apple); //Add 1 (the default) apple to the cart
$cart->addItem($apple, 2); //Add 2 more apples
//the cart should now contain 3 apples
```

*Delete products from the cart*

It should be possible to delete products from the cart. The delete method should also take an optional quantity parameter where you can specify
how many items you want to delete (default is to delete all items of that type). If the user tries to delete an product that does not exists the application should throw some kind of error.

*Get cart totals*

Add two methods to the cart. One should return total numbers of items and the other one should return the total cost of all items.

```
$cart = new Cart();
$apple = new Product(1, "Apple", 5); //Apples costs 5
$banana = new Product(2, "Banana", 10); //Bananas costs 10
$cart->addItem($apple, 2); //Add 2 apples
$cart->addItem($banana, 3); //Add 3 bananas
$cart->getTotalQuantity(); //Should return 5
$cart->getTotalCost(); //Should return 40
```

*Add discount*

It should be possible to add a discount (in percent) to the cart

```
$cart = new Cart();
$cart->addItem(new Product(1, "Apple", "10"));
$cart->addDiscount(0.10); //Add a 10% discount to all items in the cart
$cart->getTotalCost(); //Should return 9
```

*Save and load cart*

In the final task you should add functionality to save and load the cart to a string. On a real site this can be used to store the cart to the
session or in the database.

```
//Save cart sample
$cart = new Cart();
//Add some items to the cart...
$data = $cart->save();
//$data should be a string that contains all important information from the cart (items, discounts etc)

//Load cart sample
$data = '...'; //a string with cart data (items, discounts etc)
$cart = new Cart();
$cart->load($data);
```

Submission
----------
Please submit your solution via a zip file to martin@photowall.se
