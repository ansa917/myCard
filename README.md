# myCard
C++ Deck of Cards
#include <iostream>
using namespace std;
#include <string>


struct Card{
  string cardName;
  string suit;
  int cardValue;
};


void getCardName(Card &myCard);
void getSuit(Card &myCard);


int main( )
{
    int score = 0;
    srand((unsigned) time(0));

    Card *Pack;
    Pack = new Card[52];
    string guess;

    //each element assigned a number between 1 and 13
    for (int index = 0; index < 52; index++){
       Pack[index].cardValue=1 + (rand()% 13);
    }

    for (int index = 0; index < 52; index++){
      getCardName(*(Pack + index));
    }

    for (int index = 0; index < 52; index++){
      getSuit(*(Pack + index));
    }


    for (int index = 0; index < 10; index++){
        int myNum = rand() % 52;
        Card myCard = *(Pack + myNum);
        
         
      //comment out on live version 

      cout << "For Testing - " << myCard.cardName << " of " << myCard.suit<< "\n\n";
      
        
        int temp = 1 + (rand() % 10);
        cout << "Higher or Lower than " << temp <<endl;
        getline(cin, guess);
        //in live version identify the number is higher or lower then value showing in the game.

        if (guess == "lower" && (temp > myCard.cardValue)){
          cout << "correct\n";
          score ++;
        }
       else if (guess == "higher" && (temp < myCard.cardValue)){
          cout << "correct\n";
          score ++;
        }
        // after identify the correct answer it will add point to player score card.
        else{
          cout << "wrong!\n";
        }


        cout << "It was the " << myCard.cardName << " of " << myCard.suit<< "\n\n";
        cout <<"scored: " << score << endl;
    }
    
   // after modifying the value is lower or higher it will show correct or wrong and will score for player .
    cout <<"your final scored: " << score;

    return 0;
    // in the end of the game you will see your final score
}

 // in these constructors about getCardName name or number has assigned for myCard
 void getCardName(Card &myCard){
   if(myCard.cardValue == 1) {
      myCard.cardName = "Ace";
   }
  else if(myCard.cardValue == 2) {
      myCard.cardName = "Two";
   }
   else if(myCard.cardValue == 3) {
      myCard.cardName = "Three";
   }
   else if(myCard.cardValue == 4) {
      myCard.cardName = "Four";
   }
   else if(myCard.cardValue == 5) {
      myCard.cardName = "Five";
   }
  else if(myCard.cardValue == 6) {
      myCard.cardName = "Six";
   }
   else if(myCard.cardValue == 7) {
      myCard.cardName = "Seven";
   }
   else if(myCard.cardValue == 8) {
      myCard.cardName = "Eight";
   }
   else if(myCard.cardValue == 9) {
      myCard.cardName = "Nine";
   }
  else if(myCard.cardValue == 10) {
      myCard.cardName = "Ten";
   }
  else if(myCard.cardValue == 11) {
      myCard.cardName = "Jack";
   }
  else if(myCard.cardValue == 12) {
      myCard.cardName = "Queen";
   }
  else if(myCard.cardValue == 13) {
      myCard.cardName = "King";
   }
 }
 // these constructors about getSuit for myCard

void getSuit(Card &myCard){
  int temp = 1 + (rand() % 4);
  if (temp == 1) {
    myCard.suit = "Hearts";
  }
  else if (temp == 2) {
    myCard.suit = "Clubs";
  }
  else if (temp == 3) {
    myCard.suit = "Diamonds";
  }
  else if (temp == 4) {
    myCard.suit = "Spades";
  }
}
 
