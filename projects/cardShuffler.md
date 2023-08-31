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


Micromouse is an event where small robot “mice” solve a 16 x 16 maze.  Events are held worldwide.  The maze is made up of a 16 by 16 gird of cells, each 180 mm square with walls 50 mm high.  The mice are completely autonomous robots that must find their way from a predetermined starting position to the central area of the maze unaided.  The mouse will need to keep track of where it is, discover walls as it explores, map out the maze and detect when it has reached the center.  having reached the center, the mouse will typically perform additional searches of the maze until it has found the most optimal route from the start to the center.  Once the most optimal route has been determined, the mouse will run that route in the shortest possible time.

For this project, I was the lead programmer who was responsible for programming the various capabilities of the mouse.  I started by programming the basics, such as sensor polling and motor actuation using interrupts.  From there, I then programmed the basic PD controls for the motors of the mouse.  The PD control the drive so that the mouse would stay centered while traversing the maze and keep the mouse driving straight.  I also programmed basic algorithms used to solve the maze such as a right wall hugger and a left wall hugger algorithm.  From there I worked on a flood-fill algorithm to help the mouse track where it is in the maze, and to map the route it takes.  We finished with the fastest mouse who finished the maze within our college.

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
