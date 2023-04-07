#include <stdio.h>

#define MAX_PLAYERS 11

struct Player {
   char name[50];
   int runs;
};

int main() {
   struct Player team[MAX_PLAYERS];
   int totalRuns = 0;

   printf("Enter batting information of %d players:\n", MAX_PLAYERS);

   for (int i = 0; i < MAX_PLAYERS; i++) {
      printf("Enter name of player %d: ", i+1);
      scanf("%s", team[i].name);

      printf("Enter runs scored by player %d: ", i+1);
      scanf("%d", &team[i].runs);

      totalRuns += team[i].runs;
   }

   printf("\nTotal runs scored by the team: %d\n", totalRuns);

   return 0;
}
