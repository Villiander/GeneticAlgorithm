# Psudeo Code

Set TARGET to the desired text
Set POPULATION_SIZE to 100
Set MAX_GENERATIONS to 1000000
Set TOURNAMENT_SIZE to 3
Set MUTATION_RATE to 0.2
Set CROSSOVER_RATE to 0.4
Define a pool of CHARACTERS that includes all unique characters from TARGET

Function GENERATE_INDIVIDUAL:
    Create an individual string of random characters from CHARACTERS pool
    The length of the individual is the same as TARGET
    Return the individual

Function FITNESS:
    Take an individual as input
    Compare it with TARGET, character by character
    Count the number of characters that match
    Return the count as the fitness score

Function CROSSOVER (parent1, parent2):
    Choose a random point in the string
    Create two new children by combining parts of parents at the crossover point
    Return the children

Function MUTATE (individual, mutation_rate):
    For each character in the individual:
        With a probability defined by mutation_rate, replace it with a random character from CHARACTERS pool
    Return the mutated individual

Function SELECT_PARENTS (population, tournament_size):
    Select a random subset of the population of size tournament_size
    Return the individual with the highest fitness from this subset

Function SURVIVAL_SELECTION (population, offspring):
    Combine population with offspring
    Sort combined group by fitness in descending order
    Return the top individuals equal to the population size

Function GENETIC_ALGORITHM:
    Initialize a population of random individuals using GENERATE_INDIVIDUAL
    Repeat for MAX_GENERATIONS or until TARGET is matched:
        Evaluate each individual's fitness using FITNESS function
        If the best individual matches TARGET, return the current generation number
        Select parents using SELECT_PARENTS function
        Generate offspring by crossing over parents and mutating the results
        Select the new population using SURVIVAL_SELECTION function
    If TARGET is not matched, return -1

Run GENETIC_ALGORITHM with specified parameters
Print "Solution Found" and generations required if a solution is found
Otherwise, print "No solution found"
