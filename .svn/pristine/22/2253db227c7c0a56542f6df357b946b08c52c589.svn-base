package mboles.cardgame_war;
/*
 * Written by Matthew Boles
 */

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Card 
{
	private int rank;
	private int deckRank;
	private int winner;
	private int player1R, player2R;
	private int player1TieR1, player1TieR2, player1TieR3;
	private int player2TieR1, player2TieR2, player2TieR3;
	private boolean tie;
	private String cardFlag;
	private String p1CardFlag, p2CardFlag;
	private String p1TieFlag1, p2TieFlag1, p1TieFlag2, p2TieFlag2, p1TieFlag3, p2TieFlag3;
	private ArrayList<Card> initialList;
	private ArrayList<Card> fullDeck;
	private ArrayList<Card> player1Deck;
	private ArrayList<Card> player2Deck;
	private List<Card> split1;
	private List<Card> split2;
	
	public Card(int rank, String cardFlag)
	{
		this.rank = rank;
		this.cardFlag = cardFlag;
	}
	
	public Card()
	{
		/*
		 * Initialize ArrayLists that will be used later 
		 */
		initialList = new ArrayList<Card>();
		fullDeck = new ArrayList<Card>();
		player1Deck = new ArrayList<Card>();
		player2Deck = new ArrayList<Card>();
		
		/*
		 * Initialize variables
		 */
		player1R = 0;
		player2R = 0;
		p1CardFlag = "";
		p2CardFlag = "";
		
		player1TieR1 = 0;
		player1TieR2 = 0;
		player1TieR3 = 0;
		
		player2TieR1 = 0;
		player2TieR2 = 0;
		player2TieR3 = 0;
		
		tie = false;
	}
	
	public String getCardFlag()
	{
		return cardFlag;
	}
	
	public String getP1CardFlag()
	{
		return p1CardFlag;
	}
	
	public String getP2CardFlag()
	{
		return p2CardFlag;
	}
	
	public int getPlayer2Rank()
	{
		return player2R;
	}
	
	public int getPlayer1Rank()
	{
		return player1R;
	}
	
	public int getRank()
	{
		return rank;
	}
	
	public int getWinner()
	{
		return winner;
	}
	
	public int getPlayer1TieR()
	{
		return player1TieR1;
	}
	
	public int getPlayer1TieR2()
	{
		return player1TieR2;
	}
	
	public int getPlayer1TieR3()
	{
		return player1TieR3;
	}
	
	public int getPlayer2TieR()
	{
		return player2TieR1;
	}
	
	public int getPlayer2TieR2()
	{
		return player2TieR2;
	}
	
	public int getPlayer2TieR3()
	{
		return player2TieR3;
	}
	
	public int getPlayer1Count()
	{
		return player1Deck.size();
	}
	
	public int getPlayer2Count()
	{
		return player2Deck.size();
	}
	
	public boolean getTie()
	{
		return tie;
	}
	
	public void setTie(boolean t)
	{
		tie = t;
	}
	
	public String getP1TieFlag1() {
		return p1TieFlag1;
	}

	public String getP2TieFlag1() {
		return p2TieFlag1;
	}

	public String getP1TieFlag2() {
		return p1TieFlag2;
	}

	public String getP2TieFlag2() {
		return p2TieFlag2;
	}

	public String getP1TieFlag3() {
		return p1TieFlag3;
	}

	public String getP2TieFlag3() {
		return p2TieFlag3;
	}
	
	public void createAndSplit()
	{
		for(int i = 0; i <= 12; i++)
		{
			deckRank = i + 2;
			
			String h = "Hearts";
			String d = "Diamonds";
			String s = "Spades";
			String c = "Clubs";
			
			Card heartList = new Card(deckRank, h + deckRank);
			Card diamondsList = new Card(deckRank, d + deckRank);
			Card spadesList = new Card(deckRank, s + deckRank);
			Card clubsList = new Card(deckRank, c + deckRank);
			
			initialList.add(heartList);
			initialList.add(diamondsList);
			initialList.add(spadesList);
			initialList.add(clubsList);
		}
		
		/*
		 * InitialList is creating all the cards with their suit
		 * FullDeck holds all the cards in one ArrayList Collection
		 * Collections.shuffle will shuffle list before splitting
		 * List split1 and split2 are sublists of FullDeck
		 * subList(fromEndex, toIndex) --> toIndex is up to that index, does not include index
		 * Player1Deck and Player2Deck are populated from the shuffled and split lists
		 * 
		 * DON'T FORGET TO INITIALIZE COLLECTIONS(ARRAYLIST, LIST, ETC)
		 */
		
		fullDeck.addAll(initialList);
		Collections.shuffle(fullDeck);
		split1 = fullDeck.subList(0, 26);
		split2 = fullDeck.subList(26, 52);
		player1Deck.addAll(split1);
		player2Deck.addAll(split2);
		
		System.out.println("Success");
	}
	
	public void Compare()
	{
		player1R = player1Deck.get(0).getRank();
		p1CardFlag = player1Deck.get(0).getCardFlag();
		
		player2R = player2Deck.get(0).getRank();
		p2CardFlag = player2Deck.get(0).getCardFlag();
		
		if(player1Deck.get(0).getRank() > player2Deck.get(0).getRank())
		{
			/*
			 * Adds top card to the bottom and then removes the top card from list
			 * Adds top card from Deck2 to the bottom of Deck1
			 * Removes top card from Deck2 completely
			 */
			winner = 1;
			player1Deck.add(player1Deck.get(0));
			player1Deck.remove(0);
			player1Deck.add(player2Deck.get(0));
			player2Deck.remove(0);
		}
		else if(player1Deck.get(0).getRank() < player2Deck.get(0).getRank())
		{
			winner = 2;
			player2Deck.add(player2Deck.get(0));
			player2Deck.remove(0);
			player2Deck.add(player1Deck.get(0));
			player1Deck.remove(0);
		}
		else
		{
			tie = true;
			TieBreaker();
		}
	}
	
	public void TieBreaker()
	{
		player1TieR1 = player1Deck.get(2).getRank();
		p1TieFlag1 = player1Deck.get(2).getCardFlag();
		
		player2TieR1 = player2Deck.get(2).getRank();
		p2TieFlag1 = player2Deck.get(2).getCardFlag();
		
		if(player1Deck.get(2).getRank() > player2Deck.get(2).getRank())
		{
			winner = 1;
			player1Deck.add(player2Deck.get(0));
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));
			player2Deck.remove(0);
			player1Deck.add(player1Deck.get(0));
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));
			player1Deck.remove(0);
			
		}
		else if(player1Deck.get(2).getRank() < player2Deck.get(2).getRank())
		{
			winner = 2;
			player2Deck.add(player1Deck.get(0));//0
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//1
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//2
			player1Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//0
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//1
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//2
			player2Deck.remove(0);
		}
		else
		{
			tie = true;
			TieBreaker2();
		}
	}
	
	public void TieBreaker2()
	{
		player1TieR2 = player1Deck.get(4).getRank();
		p1TieFlag2 = player1Deck.get(4).getCardFlag();
		
		player2TieR2 = player2Deck.get(4).getRank();
		p2TieFlag2 = player2Deck.get(4).getCardFlag();
		
		if(player1Deck.get(4).getRank() > player2Deck.get(4).getRank())
		{
			winner = 1;
			player1Deck.add(player2Deck.get(0)); //0
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//1
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//2
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//3
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//4
			player2Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//0
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//1
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//2
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//3
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//4
			player1Deck.remove(0);
		}
		else if(player1Deck.get(4).getRank() < player2Deck.get(4).getRank())
		{
			winner = 2;
			player2Deck.add(player1Deck.get(0));//0
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//1
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//2
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//3
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//4
			player1Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//0
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//1
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//2
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//3
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//4
			player2Deck.remove(0);
		}
		else
		{
			tie = true;
			TieBreaker3();
		}
	}
	
	public void TieBreaker3()
	{
		player1TieR3 = player1Deck.get(6).getRank();
		p1TieFlag3 = player1Deck.get(6).getCardFlag();
		
		player2TieR3 = player2Deck.get(6).getRank();
		p2TieFlag3 = player2Deck.get(6).getCardFlag();
		
		if(player1Deck.get(6).getRank() > player2Deck.get(6).getRank())
		{
			winner = 1;
			player1Deck.add(player2Deck.get(0)); //0
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//1
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//2
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//3
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//4
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//5
			player2Deck.remove(0);
			player1Deck.add(player2Deck.get(0));//6
			player2Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//0
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//1
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//2
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//3
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//4
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//5
			player1Deck.remove(0);
			player1Deck.add(player1Deck.get(0));//6
			player1Deck.remove(0);
		}
		else if(player1Deck.get(6).getRank() < player2Deck.get(6).getRank())
		{
			winner = 2;
			player2Deck.add(player1Deck.get(0));//0
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//1
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//2
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//3
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//4
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//5
			player1Deck.remove(0);
			player2Deck.add(player1Deck.get(0));//6
			player1Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//0
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//1
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//2
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//3
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//4
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//5
			player2Deck.remove(0);
			player2Deck.add(player2Deck.get(0));//6
			player2Deck.remove(0);
		}

	}

}
