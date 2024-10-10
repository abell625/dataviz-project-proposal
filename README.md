# Data Visualization Project

## Data

The data I propose to visualize for my project is a Pokemon GO dataset that can be found at https://www.kaggle.com/datasets/shreyasur965/pokemon-go?resource=download


## Questions & Tasks

The following tasks and questions will drive the visualization and interaction decisions for this project:

 * I want to see how many pokemon have special methods of finding them (i.e. found_egg, found_research etc.)
 * I want to see how different pokemon's max strength (max_cp) correlates to other fields (base_capture_rate, etc.)
 * I want to see how different pokemon's move sets vary across different stages of evolution.

## Sketches

![DataVizProposalSketch](https://github.com/user-attachments/assets/2af745b7-efb4-4ff4-991f-5ca8afbaeb6d)

In this rough diagram of the dataset, I show different stats of a particular pokemon as a radar chart, a level curve which will display a pokemon's max strength at every level, and a few symbols which will display which pokemon can be captured by different methods. The different methods of obtaining come from eggs, evolution, wild captures, research breakthroughs, and raid battles. In this diagram I also leave space for different moves the pokemon can learn, as well as it's weaknesses and resistances.

## Open Questions

My biggest worry is actually the dropdown/search for a particular pokemon. I intend for it to populate with pokmemon's names from the dataset, but I'm not confident about putting it all into a dropdown menu. In addition, the symbols I plan on using for the ways to obtain might not be as clear as I hoped, so I plan on iterating them over time to make sure that the symbol's meaning is clear. Lastly, the level curve is going to originate from a formula based on the stats of the pokemon, so I have to make sure that the formula is accurate to the game information.

## Milestones

Week 1: Implement radar chart, ways to obtain, fast attack list, and charged attack list.

Week 2: Implement weaknesses & resistances lists

Week 3: Implement level curve

Week 4: Implement Dropdown to search different pokemon

Week 5: Catchup on any incomplete tasks, implement any last minute ideas.
