# smms_docs
  
<h1>Tutorial</h1>

<pre>void main() {
  var deck = Deck();
  print(deck);
  //print(deck.deal(5));
  //print(deck);
  //deck.shuffle();
  //print(deck.cardsWithSuit('Diamonds'));
  deck.removeCard('Diamonds', 'Two');
  print(deck);
  
}

class Deck {
  List<Card> cards = [];
  
  Deck() {
    var ranks = [
      'Ace', 'Two', 'Three', 'Four', 'Five', 'Six', 'Seven', 'Eight', 'Nine', 'Ten', 'Jack', 'Queen', 'King'
    ];
    
    var suits = [
      'Diamonds',
      'Hearts',
      'Clubs',
      'Spades'
    ];
    
    for (var suit in suits) {
      for (var rank in ranks) {
        var card = Card(
          rank: rank, 
          suit: suit);
        cards.add(card);
      }
    }
  }
  
  @override
  toString() {
    return cards.toString();
  }
  
  shuffle() {
    cards.shuffle();
  }
  
  cardsWithSuit(String suit) {
    return cards.where((card) => card.suit == suit);
  }
  
  deal(int handSize) {
    var hand = cards.sublist(0, handSize);
    cards = cards.sublist(handSize);
    
    return hand;
  }
  
  removeCard(String suit, String rank) {
    return cards.removeWhere((card) => (card.suit == suit) && (card.rank == rank));
  }
}

class Card {
  String suit;
  String rank;
  
  Card({this.rank, this.suit});
  
  @override
  String toString() {
    return '${rank} of ${suit}';
  }
}</pre>
