---
layout: project
type: project
image: img/vendingMachineLogo.jpg
title: "Virtual Vending Machine"
date: 2021
published: true
labels:
  - Simulation
  - User Input
  - Java
summary: "I developed a Java program that initialized a virtual vending machine which allowed user input"
---

As a project for my ICS 212, I've created a program that simulates a vending machine and retrieves items from that vending machine. This project allowed me to explore the ideas of classes and objects and the interpolation of the two in one program. As a quick explanation of how the program works, I created a vending machine class that took the input of monetary values and a number, that simulated the choice and money inserted into the vending machine. This class then also “dispensed” whatever the user inputted, while also showing errors if the machine didn’t have the desired candy, or didn’t intake the desired amount of money.

One issue that I ran into while creating this project was using the try-and-catch function in C++ if the user had thrown an exception. This was easily solved when I learned more about how the try-and-catch function works. While working on this program I extended my knowledge of Java overall and learned new functions and how to construct a project using both classes and objects

Here is a snippet of the code that was used to create the vending machine function.

```java

public class VendingMachine {

  public static void main(String[] args) {

    // Invalid candy bar name in constructor.
    try {
      CandyBar snickers = new CandyBar("", "Mars, Incorporated", 1, 250);
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }
    
    // Invalid candy bar name in mutator method.
    try {
      CandyBar snickers = new CandyBar("Snickers", "Mars, Incorporated", 1, 250);
      snickers.setName("");
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }

    // Invalid company in constructor.
    try {
      CandyBar snickers = new CandyBar("Snickers", "", 1, 250);
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }
    
    // Invalid company in mutator method.
    try {
      CandyBar snickers = new CandyBar("Snickers", "Mars, Incorporated", 1, 250);
      snickers.setCompany("");
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }

    // Invalid serving size in constructor.
    try {
      CandyBar snickers = new CandyBar("Snickers", "Mars, Incorporated", 0, 250);
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }
    
    // Invalid serving size in mutator method.
    try {
      CandyBar snickers = new CandyBar("Snickers", "Mars, Incorporated", 1, 250);
      snickers.setServingSize(-500);
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }

    // Invalid calories in constructor.
    try {
      CandyBar snickers = new CandyBar("Snickers", "Mars, Incorporated", 1, -1);
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }
    
    // Invalid calories in mutator method.
    try {
      CandyBar snickers = new CandyBar("Snickers", "Mars, Incorporated", 1, 250);
      snickers.setCalories(-250);
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }

    // Valid candy bar.
    try {
      CandyBar snickers = new CandyBar("Snickers", "Mars, Incorporated", 1, 250);
      System.out.println("Success, candy bar created: ");
      System.out.println(snickers);
    }
    catch (CandyBarException cbe) {
      System.out.println(cbe);
    }

  }

}

```
