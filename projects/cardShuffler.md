---
layout: project
type: project
image: img/cardShufflerLogo.jpg
title: "Card Shuffler"
date: 2021
published: true
labels:
  - Simulation
  - Randomizer
  - C
summary: "I developed a C program that simulated/displayed the shuffling of a deck of cards using structures and typedef"
---


As a project for my ICS 212 class, I designed a C++ program that utilized my knowledge of structures and classes that simulated the shuffling of a deck of cards. Some things that I used in this program were macros, and directives that linked to other files and functions outside of my program. As a general description, what my code did to achieve this simulation was create a card structure, that contained information such as rank, suit, and color of each card. With that structure, I used 1 and 2-dimensional arrays of strings that were used to assign the cards to their respective information. You can see the process of initializing each card with the correct information in the chunk of code below. 

An issue that I ran into while creating this program was the inclusion of srand in my program. Srand was a function in C++ that generated a random number, which was the main function for creating a random order for the cards. What was unique about this function was its usage of a seed value. It required a directive from time.h and stdlib.h, which took the current time and date as a runtime value for the random number it generated. Getting used to understanding how srand worked and how it created a random number was a challenge for me. But overall, I am proud of how the program runs, and I felt that I wrote the code in an efficient manner.


Here is a snippet of code where I created the structure of the card, and initialized the deck of cards

```cpp

//structure definition
struct card{ 
  char *rank;    
  char suit[MAX];
  char *color;  
};
typedef struct card Card;

void initialize(Card deck[]){
  int i = 0;
  for(i=0;i<MAX_CARDS;i++){
    deck[i].rank = ranks[i%MAX_RANKS];
    strncpy(deck[i].suit, suits[i/MAX_RANKS], MAX);
    if((strcmp(deck[i].suit,suits[0])==0)||(strcmp(deck[i].suit,suits[3])==0)){//if the card's suit is clubs or spades
	deck[i].color = colors[0];//make the cards color black
    }else{
	deck[i].color = colors[1];//make the cards color red
    }
  }
}

```
