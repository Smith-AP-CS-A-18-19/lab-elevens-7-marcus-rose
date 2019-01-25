# Elevens 7

Follow the instructions provided for Activity 7 in the student lab guide. This is more of an exploratory lab, so you will not need to copy any of your previous code into the repo. Answer the questions from the Student Guide in this document and ensure that you save and push the repo. You have one week to complete this lab.

1. What items would be necessary if you were playing a game of Elevens at your desk (not on the computer)? List the private instance variables needed for the `ElevensBoard` class.

    You would need a deck of cards, the suits, point-values, the number of cards on the board, and finally, the board size.

2. Write an algorithm that describes the actions necessary to play the Elevens game.

    1. You first would need to create a new game
    2. Ensure there are 9 cards on the board. If this is true, draw nine cards. Else, draw the other cards in the deck.
    3. Check to find two cards that add up to eleven. If those two cards are present, replace the cards. If the two cards do not exist, you lose the game.
    4. Repeat the previous two steps until there are no more cards in the deck.
    8. When this step is reached, you win the game.

3. Now examine the partially implemented `ElevensBoard.java` file found in this repository. Does the `ElevensBoard` class contain all the state and behavior necessary to play the game?

    Yes. All the variables needed to play are initialized as instance variables. The algorithm, or set of instructions, is correctly executed.

4. `ElevensBoard.java` contains three helper methods. These helper methods are private because they are only called from the ElevensBoard class.

  * a. Where is the `dealMyCards` method called in ElevensBoard?

      The dealMyCards() method is called in the newGame() method (and in the constructor, initializing a new game).

  * b. Which `public` methods should call the `containsPairSum11` and `containsJQK` methods?

      The anotherPlayIsPossible() method and the isLegal() method.

  * c. It’s important to understand how the `cardIndexes` method works, and how the list that it returns is used. Suppose that `cards` contains the elements shown below. Trace the execution of the `cardIndexes` method to determine what list will be returned. Complete the diagram below by filling in the elements of the returned list, and by showing how those values index `cards`. Note that the returned list may have less than 9 elements.

    * `cards`

| 0  | 1  |  2   | 3  |  4   |  5   | 6  | 7  |  8   |
|:--:|:--:|:----:|:--:|:----:|:----:|:--:|:--:|:----:|
| J♥ | 6♣ |`null`| 2♠ |`null`|`null`| A♠ | 4♥ |`null`|

   *  0, 1, 3, 6, 7

| 0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|    |    |    |    |    |    |    |    |    |

  * d. Complete the following `printCards` method to print all of the elements of cards that are indexed by `cIndexes`.

```java
public static printCards(ElevensBoard board) {
    List<Integer> cIndexes = board.cardIndexes();
    for (Integer i : cIndexes) {
      System.out.println(board.cards[i].toString());
}
```

  // (see above code for answer)

  * e. Which one of the methods that you identified in question 4b above needs to call the `cardIndexes` method before calling the `containsPairSum11` and `containsJQK` methods? Why?

     The anotherPlayIsPossible() method needs to call the cardIndexes method before containsPairSum11 method so it can check to see if there are still the right amount of cards on the board that sum to 11. If the other method was called first, there would be no point because there could be an instance where the game might not be able to continue at all, since none of the cards on the board would sum to 11.

## Feedback
Very good
20/20
