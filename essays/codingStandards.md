Y0uC@N probab!y r3ad th!sS3nt3nc3,but!tMight be a!ot h@rderth@nusua!.

In one quick sentence, I just described the importance of having a coding standard.

My professor in my Software Engineering class preaches the importance of having a good coding standard for all of our code, and I definitely agree. Before someone can understand what our code does, without a good coding standard, the person needs to
overcome the additional obstacle of deciphering the format of our code. By implementing a coding standard, we craft a convention for coding that enables us (and others reading our code) to have a clear understanding of the code we create.

Let’s take a quick look at code that has a coding standard, vs. code that doesn’t implement a coding standard:

Without coding standard:

```
class Score{
 constructor(judge, score) {
 this.judge = judge;
this.score = score;
} }

class Ride{
  constructor(surfer){
this.surfer = surfer; this.allScores = [];
}      addScore(score) {
this.allScores.push(score);}
printAllScores() { for (const lmnt of this.allScores) {
    console.log(`${lmnt.judge} gave a score of ${lmnt.score}`);
    }
  }

printOverallScore() {
let totalScore = 0;
this.allScores.sort();
for (let i = 1; i < this.allScores.length - 1; i++) {
totalScore += this.allScores[i].score;
}
totalScore /= 3;
console.log(totalScore);
  }
}
```

With coding standard:

```
class Score {
  constructor(judge, score) {
    this.judge = judge;
    this.score = score;
  }
}

class Ride {
  constructor(surfer) {
    this.surfer = surfer;
    this.allScores = [];
  }

  addScore(score) {
    this.allScores.push(score);
  }

  printAllScores() {
    for (const lmnt of this.allScores) {
      console.log(`${lmnt.judge} gave a score of ${lmnt.score}`);
    }
  }

  printOverallScore() {
    let totalScore = 0;
    this.allScores.sort();
    for (let i = 1; i < this.allScores.length - 1; i++) {
      totalScore += this.allScores[i].score;
    }
    totalScore /= 3;
    console.log(totalScore);
  }
}
```

The first example was made terribly on purpose, but you could see how for the second block of code, it is much easier to tell where a function starts and ends, what segment of code is a class, and where the for loop in a function is. Having a set
coding standard will make reading code a lot easier.

For our software engineering class, we are working on a module that completely focuses on developing a good coding standard. Personally, the initial setup for creating this coding standard was a bit tedious, but the end result of having standardized
formatting for my code made it worthwhile. For the class, we used node.js and ESlint to create the formatting within our IDE. I thought that the process of integrating the coding standard served also as a good review for using the command window
since we haven’t used it for a while in class. Regarding using ESlint, there is some initial stress while using it because I am uncomfortable with the format that it requires of me. In high school, our teacher allowed us to have our own ‘coding
standard’ for coding. While they did give us a general format for how code is usually written, as long as we can create code that is generally understandable, the formatting wasn’t a huge issue for us. So with that in mind, there were a lot of coding
habits that I developed over the years that I needed to break in order to get used to the new formatting.

What I particularly enjoy about using this coding style is how IntelliJ will give us the syntax error name, and the steps we need to follow in order to fix it. While it might enable users to correct the syntax without thinking about it, I also think that this feature allows us to better comprehend what the issue is and develop a habit of decreasing the syntax errors. Without this feature, seeing a red line under the syntax error would be very stressful to fix, because I would be unsure exactly what the problem is. But by letting me know I needed a space in this area, or need to remove that colon, I can remember the next time I code, to not make that same mistake again. So developing a coding style is definitely a gradual thought process, but by giving it some time to understand each error thoroughly, we can write code with a coding style, with minimal errors in the future. 
