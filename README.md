# Data Visualization Project

## Project Desctiption

This project uses a Pokemon Go dataset found on Kaggle
(https://www.kaggle.com/datasets/shreyasur965/pokemon-go?resource=download)
and creates a few different graphs/tables based on the
information present in the dataset. When first loading the
Visualization, it loads to Bulbasaur (Pokemon ID 1) and
presents four different important bits of information. The initial view can be seen here ![Initial View](https://github.com/abell625/dataviz-project-proposal/blob/master/VizPic1.PNG) The
first at the very top of the visualization, it shows the
selected Pokemon's name, ID and typing. Moving to the top
left, a radar chart shows how the pokemon's base stats
compare to the max of all pokemon for each stat, as well as
the actual numbers behind it. The top right has a graph that
looks similar for most pokemon, but shows how the pokemon's
CP grows as it levels up. On the default view, it will label
the CP at levels 1, 10, 20, 30, and 51, however this can be
changed to an absolute value where the top of the graph is
determined by the pokemon with the highest CP. Here is a picture of the same pokemon in the absolute graph mode ![Absolute mode](https://github.com/abell625/dataviz-project-proposal/blob/master/VizPic2.PNG) In this case,
since there are many pokemon with maximum CP compared to the
maximum, we only display the pokemon's max CP due to
potential overlapping text. Lastly, there is a table on the
bottom left that has Type effectiveness matchups as well as
the moves it can learn. In the type effectiveness table, it
also lists the precise effectiveness of moves against that
pokemon. Note that the type effectiveness in Pokemon Go is
very different from the mainline Pokemon games. Different values of resistances and weaknesses can be found in the image here ![Resistances and Weaknesses](https://github.com/abell625/dataviz-project-proposal/blob/master/VizPic3.PNG) Note how the lowest possible effective value (0.244x) has an asterisk to indicate that it is very ineffective, and bold and normal text are used to differentiate the type effectiveness otherwise. For more details on that, read more in my Week 4 Progress section. At the very
top, there are two dropdown menus and a input box. The first
dropdown menu selects a pokemon based on it's name. The
second dropdown controls the graph on the top right's
setting. The input box allows you to quickly type in a
pokemon's name or ID number and it'll load that pokemon. Overall, I am happy with how this project turned out, but I still have a few changes I would have liked to make if I had more time.

A video presentation of my work can be found at https://youtu.be/0B7rYtYP35o?si=WYtS_56ftcM5VX3W

### Future Work

I was unable to find the time to make the dropdowns and
input box at the top as pretty as I would've like, but as of
now they are functional and that matters more than being
pretty for it's purpose. In addition, Pokemon who have a Max
CP equal to or close to the Max CP of the strongest pokemon
(Currently Zacian, ID = 888) will still have an issue of
overlapping text when in the absolute view on the level
scaling graph. ![Glitched Text](https://github.com/abell625/dataviz-project-proposal/blob/master/VizPic4.PNG) I'm sure there is
a fix for this, but I cannot think of it at the moment. I
also cut the "methods of obtaining pokemon" that was present
in my original sketch because I'm not sure I had the ability
to make those complicated shapes look good and still hold
what they were supposed to be, and because those fields were
often misleading or incorrect entirely for any given
pokemon. Lastly, the moves do not contain any specific
information on them. I would've loved to include more
information on the moves, however I could not find a dataset
that contains information on all the moves in Pokemon Go, so
for now it will remain as a future work opportunity.

# Weekly Progress

## Week 1 Progress

Unfortunately, due to a slew of other projects and problems,
I didn't really have time to work much on this step. I will
continue to work as I am freed up.

## Week 2 Progress

This week I managed to complete Week 1's tasks. Now the
Selected Pokemon (default is Bulbasaur) will display the
appropriate radar chart. Also, I removed 3 pokemon from the
pokemon.csv since they had invalid data for their stats in
these categories. These pokemon were ID = 679, 680, & 681.
Currently, the page does not refresh properly when changing
values in the viz, causing it to redraw over the old viz.
This means that the whole page must be refreshed in order to
see proper changes. I'm not currently sure what causes this,
but I will investigate soon.

## Week 3 Progress

This week, I decided to skip ahead to Week 4's tasks. Now,
there is a dropdown menu where you can select a pokemon
based on it's name. This dropdown menu populates with all
pokemon names in the pokemon.csv file. In addition, I
removed one extreme outlier (Eternatus, ID = 890) from the
pokemon.csv, due to it's extremely high Max CP. I cleaned up
the existing code to be slightly easier to work with in my
opinion. Lastly, I solved the redraw bug that I had last
week, as well as a bug related to the radar chart not
drawing properly that I did not know about, which is part of
the reason I decided to implement the dropdown menu this
week. For next week, I hope to implement the
Weaknesses/resistances & move pools, which should add some
color to the visualization (I know that was this weeks
assignment, but I felt this was more important to complete
this week).

## Week 4 Progress

This week, I implemented the movepool lists, matchups table,
weaknesses/resistances, a level curve which can be scaled to
be relative or absolute, and added some colors to the
visualization. The movepool lists were relatively trivial,
however I am unable to get information on individual moves,
so I cannot change their color based on the type of the move
listed (which is something I would have done if possible).
For the Matchup table, I made a matrix 18x18 which contains
information on every type's defenses versus an enemy attack
of any type. This was mindless, but time consuming, as I had
to input all 324 possibilities by hand. I also added a table
which tracks a pokemon type with a corresponding hex color,
which are the official type colorings used in the games &
materials. Once I had finished that, I added colors to the
types in the resistances and weaknesses lists, which also
differentiates if a move is "super effective", "very
effective" (Both types are weak to a given attacking type),
"not very effective", "ineffective" (Either both types
resist or one type is immune to a given attacking type), or
"very innefective" (One type is immune, the other is
resistantto a given attacking type) by using bold for Very
effective, ineffective, and very ineffective, as well as
adding an asterisk to the text if a pokemon has any "Very
innefective" resistances.

As for the level curve, I was able to reuse the invlerp
function I made for the radar chart which helped a lot. The
formula is a lot to look at, but it wasn't too hard to
implement since it is well documented online. I managed to
complete the level curve, at which point I realized it's not
as much of a curve as I would have guessed, but rather a
compound function consisting of two lines (it's techically
more, but there's a stark contrast between levels 1-30 and
30.5-51). I marked a line at level 30 to better show this,
as well as other notable points on the graph. I also decided
to use the secondary typing for the level curve if the
pokemon has two types.

Lastly, As I was looking through the data more closely, I
realized that for many pokemon which have alternate forms,
it uses that alternate form instead of the original. For
example, the pokemon Voltorb, which is normally just an
electric type, is listed as an electric/grass type in the
CSV. This also may effect the default stats of some pokemon,
which can be seen in Mewtwo, which has the alternate form
called "Armored Mewtwo". Regular Mewtwo has base 300 Attack,
182 Defense, and 214 Stamina, as compared to Armored Mewtwo
which has base 182 Attack, 278 Defense, and 214 Stamina,
which is what displays in the visualization. Unforunately,
there are no ways to see the regular forms of pokemon in the
csv I used, so I will have to settle for this in my
visualization.

## Week 5 Progress

Since I was pretty happy with my progress from last week, I
used this week to make minor changes to the visualization.
Firstly, I added the multiplier number itself on the
weaknesses & resistances, for better clarity. In addition,
in the relative scaling view of the level curve, I added
more info on what the CP is of the pokemon at levels 10, 20,
and 30. Lastly, I added a couple of functions that would
help with redundant pieces of code in order to clean it up a
small amount. I also fixed a minor errror with Bug type
pokemon's weaknesses and resistances. For next week, I plan
on adding a number entry box as an alternative to using the
dropdown menu to find a pokemon.

## Week 6 Progress

This week, I set out what I wanted to do by adding an input
box at the top that will allow users to type in an ID or
pokemon name. The pokemon name must be an exact match,
however it does not check for capitalization. Names of
pokemon including unusual characters, such as "Ho-Oh" and
"Brute Bonnet", still worked as intended. As a reminder,
some pokemon were removed due to missing stats or extreme
outlier case. These Pokemon are ID numbers 679, 680, 681,
and 890.

Also, as I tested some pokemon, I noticed that their moves
(Fast/Charged attacks) were essentially dummy data, however
this is again an issue I cannot fix easily with my data,
especially since these pokemon haven't yet been made
available in the official game.

# Initial Proposal

## Data

The data I propose to visualize for my project is a Pokemon
GO dataset that can be found at
https://www.kaggle.com/datasets/shreyasur965/pokemon-go?resource=download

## Questions & Tasks

The following tasks and questions will drive the
visualization and interaction decisions for this project:

- I want to see how many pokemon have special methods of
  finding them (i.e. found_egg, found_research etc.)
- I want to see how different pokemon's max strength
  (max_cp) correlates to other fields (base_capture_rate,
  etc.)
- I want to see how different pokemon's move sets vary
  across different stages of evolution.

## Sketches

![DataVizProposalSketch](https://github.com/user-attachments/assets/2af745b7-efb4-4ff4-991f-5ca8afbaeb6d)

In this rough diagram of the dataset, I show different stats
of a particular pokemon as a radar chart, a level curve
which will display a pokemon's max strength at every level,
and a few symbols which will display which pokemon can be
captured by different methods. The different methods of
obtaining come from eggs, evolution, wild captures, research
breakthroughs, and raid battles. In this diagram I also
leave space for different moves the pokemon can learn, as
well as it's weaknesses and resistances.

## Open Questions

My biggest worry is actually the dropdown/search for a
particular pokemon. I intend for it to populate with
pokmemon's names from the dataset, but I'm not confident
about putting it all into a dropdown menu. In addition, the
symbols I plan on using for the ways to obtain might not be
as clear as I hoped, so I plan on iterating them over time
to make sure that the symbol's meaning is clear. Lastly, the
level curve is going to originate from a formula based on
the stats of the pokemon, so I have to make sure that the
formula is accurate to the game information.

## Milestones

Week 1: Implement radar chart, ways to obtain, fast attack
list, and charged attack list.

Week 2: Implement weaknesses & resistances lists

Week 3: Implement level curve

Week 4: Implement Dropdown to search different pokemon

Week 5: Catchup on any incomplete tasks, implement any last
minute ideas.
