<div align="center">

## Dungeon of Despair Text Adventure


</div>

### Description

This small program is an introductory look at what can be done without knowing the full scope of a language. Any beginner should be able to duplicate this and with some imagination, blow it away.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Steven D\. Bradley](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/steven-d-bradley.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C, C\+\+ \(general\)
**Category**       |[Games](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/games__3-13.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/steven-d-bradley-dungeon-of-despair-text-adventure__3-11883/archive/master.zip)





### Source Code

```
/* The Dungeon of Despair is an introductory level look into
 C/C++ programming. It is intended to be accomplished by
 complete beginners to either language.
 for more information http://irongryphon.com*/
#include <iostream>
using namespace std;
enum
  {
  DEATH,
  ROOM1,
  ROOM2,
  ROOM3,
};
int main()
  {
  int GameState = ROOM1;
  char cChoice;
  char Name[25];
  int iRoomCounter[3] = {0,0,0}; // Used to determine if a room has been visited.
  cout << "\t\t\tWelcome to the Dungeon of Despair!" << endl;
  cout << "\nYour task is simple. Explore the dungeon and stay alive." << endl;
  cout << "One last warning. There is a rumor of a great evil within these halls. . ." << endl;
  cout << "Good Luck adventurer!" << endl;
  cout << "\nJust so the bards will know who to sing about, what is your name?" << endl;
  cout << "-> ";
  cin >> Name;
  cout << "\nThank you " << Name << ". Your deeds will not go untold." << endl;
  while(GameState != DEATH)
    {
    switch(GameState)
      {
      case ROOM1:
        {
        if(iRoomCounter[0] == 0)
          {
          cout << "\nLooking around the dimly lighted room, you notice a thick " << endl;
          cout << "layer of dust on the rough stone floor. The room is roughly " << endl;
          cout << "20 feet from East to West, and 16 from North to South. Barely " << endl;
          cout << "discernible in the dust is what appears to be tracks leading " << endl;
          cout << "through the only other exit. It is a solid looking, iron bound " << endl;
          cout << "wooden door along the East wall. \n" << endl;
          iRoomCounter[0] = 1;
        }
        cout << "\nWhat do you want to do?" << endl;
        cout << "1 - Explore the room more." << endl;
        cout << "2 - Check the wooden door." << endl;
        cout << "-> ";
        cin >> cChoice;
        if(cChoice == '1')
          {
          cout << "\nYou spend another hour searching the room but find nothing " << endl;
          cout << "of interest. Giving up, you decide to check the wooden door." << endl;
          GameState = ROOM1;
        }
        else if(cChoice == '2')
          {
          cout << "You cross the room to the wooden door. Pausing, you listen for " << endl;
          cout << "any sounds on the other side. Hearing nothing, you reach for the " << endl;
          cout << "latch. With a screech, the door opens to reveal another room. . ." << endl;
          GameState = ROOM2;
        }
        else
          {
          cout << "I am sorry but you don't seem to follow directions. You are now dead. " << endl;
          cout << "Next time, please pay attention . . ." << endl;
          GameState = DEATH;
        }
      }break;
      case ROOM2:
        {
        if(iRoomCounter[1] == 0)
          {
          cout << "\nAs you enter the room, you immediately notice a strange green glow" << endl;
          cout << "coming from a decrepit alter in the center of the polished black " << endl;
          cout << "floor. There is a slight stench of decay in the room. You also notice" << endl;
          cout << "a faint hissing sound but you are not sure where it is coming from. You" << endl;
          cout << "can see 2 doors leading out of this room. One is slightly ajar on the " << endl;
          cout << "North wall and the other is closed tight along the South wall. " << endl;
          cout << "you want to do?\n" << endl;
          iRoomCounter[1] = 1;
        }
        cout << "\nWhat do you want to do?" << endl;
        cout << "1 - Explore the room." << endl;
        cout << "2 - Check the alter. " << endl;
        cout << "3 - Check the door to the North." << endl;
        cout << "4 - Check the door to the South." << endl;
        cout << "-> ";
        cin >> cChoice;
        if(cChoice == '1')
          {
          cout << "\nCarefully, you search the room but find nothing more of interest. " << endl;
        }
        else if(cChoice == '2')
          {
          cout << "\nWhile walking up to anything that is glowing in a dungeon isn't what " << endl;
          cout << "I would have decided to do. . . it turns out to be harmless. The green " << endl;
          cout << "glow is coming from some toxic looking mushrooms. Being a boy scout " << endl;
          cout << "you alway want to be prepared so you grab one of the mushrooms in case" << endl;
          cout << "it might come in handy later.\n" << endl;
        }
        else if(cChoice == '3')
          {
          cout << "\nYou quietly creep up to the door to the North. You can see the room is " << endl;
          cout << "lighted by torches and can see several very large shadows moving around " << endl;
          cout << "within. From the angle it is hard to determine what they might be. Do you" << endl;
          cout << "want to proceed through the door? (1 = YES | 2 = NO)" << endl;
          cout << "-> ";
          cin >> cChoice;
          if(cChoice == '1')
            {
            GameState = ROOM3;
          }
        }
        else if(cChoice == '4')
          {
          cout << "\nAs you approach the door to the South, you realize that it is only a painting " << endl;
          cout << "of a door. A very well done painting but either way, try as you might, it just " << endl;
          cout << "won't open.\n" << endl;
        }
      }break;
      case ROOM3: // door to north
        {
        if(iRoomCounter[2] == 0)
          {
          cout << "\nBoldly, you walk into the room to confront the evil of the world!" << endl;
          cout << "It is a shame there is no evil here. The shadows you saw were made " << endl;
          cout << "by a couple of mice running around on a table. It is ironic that you " << endl;
          cout << "made it this far, hoping to find some evil to vanquish. I say ironic " << endl;
          cout << "because the evil has been looking for you as well. As the 7 foot tall " << endl;
          cout << "demon lich stands before you, there is no doubt that you have both found " << endl;
          cout << "what you were looking for! Out of pure spite, the lich smashes the mice " << endl;
          cout << "with one of his rotting fists and leers at you. \n" << endl;
          iRoomCounter[2] = 1;
        }
        cout << "\nWhat do you want to do?" << endl;
        cout << "1 - Run, waving your arms and screaming like a little girl." << endl;
        cout << "2 - Find a weapon to attack the lich with. " << endl;
        cout << "3 - Charge the demon with reckless abandon! " << endl;
        cout << "4 - Throw the glowing mushroom at the lich." << endl;
        cout << "-> ";
        cin >> cChoice;
        if(cChoice == '1')
          {
          cout << "\nYou stinking coward! As you turn to flee, the spirits of the unavenged mice " << endl;
          cout << "rise up and possess your body. Using you against your will, the mice make you" << endl;
          cout << "attack the lich. Unfortunately, you met the same end as they. The good news is" << endl;
          cout << "that you now have two little spirit mice to keep you company in the darkest" << endl;
          cout << "room in the Dungeon of Despair!" << endl;
          cout << "\nThanks for playing\n" <<endl;
					system("PAUSE");
          GameState = DEATH;
        }
        else if(cChoice == '2')
          {
          cout << "\nLooking around, you notice a wicked looking axe. As you reach for it, the axe " << endl;
          cout << "vanishes in a mist. It was obviously a ploy by the lich to get your focus " << endl;
          cout << "elsewhere. Well, it worked. By the time you figured out what happened, you " << endl;
          cout << "were already dead. As you watch the lich feed on your still warm corpse, " << endl;
          cout << "you see two little spirits that look like mice. if you are not mistaken, " << endl;
          cout << "it looks as though they are laughing at you. The good news is" << endl;
          cout << "that you now have two little spirit mice to keep you company in the darkest" << endl;
          cout << "room in the Dungeon of Despair!" << endl;
					system("PAUSE");
          GameState = DEATH;
        }
        else if(cChoice == '3')
          {
          cout << "\nAre you completely dense??? Didn't I tell you the lich was 7 feet tall??? OK, " << endl;
          cout << "we'll do it your way. . . You muster up all your courage and strength and " << endl;
          cout << "charge the lich. Right before you died, you could have sworn it was laughing." << endl;
          cout << "Well, even if you couldn't kill it, you should be happy that you could bring " << endl;
          cout << "some comedy to it's evil life. The good news is that you now have two" << endl;
          cout << "little spirit mice to keep you company in the darkest" << endl;
          cout << "room in the Dungeon of Despair!" << endl;
					system("PAUSE");
          GameState = DEATH;
        }
        else if(cChoice == '4')
          {
          cout << "\nLooks like you are going to die anyway, so why not. You pull the glowing " << endl;
          cout << "mushroom out of your pocket and throw it at the lich. It seems that you " << endl;
          cout << "made the correct choice. As soon as the mushroom hit the lich, his body " << endl;
          cout << "was enveloped in an eerie green glow which grew in intensity. Just when you" << endl;
          cout << "thought you could no longer stand to watch, the glow, along with the lich, " << endl;
          cout << "vanished. In the now silent room, you watched as two little mice spirits " << endl;
          cout << "floated up and vanished. You have conquered the Dungeon of Despair!" << endl;
          cout << "\nThanks for playing\n" << endl;
					system("PAUSE");
          GameState = DEATH;
        }
      }break;
      default:
        {
      }break;
    }
  }
  cout << "\n\nThis has been a Game Programming Guild Production" << endl;
	system("PAUSE");
  return 0;
}
```

