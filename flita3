#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <malloc.h>

int main(){
  int n, i, j;
  int y =0;
  int z =0;
  int A[101][101];
  FILE* flita, *flita1;
  flita = fopen("flita.txt", "r");
  scanf("%d", &n);
  for (i = 0; i < n; i++){
    for (j = 0; j < n; j++){
      fscanf(flita, "%d", &A[i][j]);
    }
  }
fclose(flita);

  flita1 = fopen("flita1.txt", "w");
  fprintf(flita1, "graph {");
  for (i = 0; i < n; i++){
    for (j = 0; j < n; j++){
      if (A[i][j] != 0){
        fprintf(flita1, "%d -- %d\n", i + 1, j + 1);
          if (A[i][j] > 1){
            fprintf(flita1, " [label = %d]\n", A[i][j]);
          }
      }
    }
  }
  fprintf(flita1, " } ");
  
  for(i = 0;  i < n; i++){
    for(j = 0; j < n; j++){
      if(A[i][j] != 0 && i != j){
        z += 1;
      }

    }
  }
  for(i = 0;  i < n; i++){
    for(j = 0; j < n; j++){
      if(A[i][j] != 0 && A[j][i] != 0 && i < j){
            z -= 1;
        }
    }
  }
  printf("Rebra:%d", z);
  
  for(i = 0;  i < n; i++){
    int x = 0;
    for(j = 0; j < n; j++){
      if(A[i][j] != 0){
        x = 1;
      }
    }
    for(j = 0; j < n; j++){
      if(A[j][i] != 0){
        x = 1;
      }
    }
    if(x != 0){
      y += 1;
    }
  }
  printf("\nVershiny:%d", y);
  int u = (y-1)*(y-2)/2;
  if(z > u){
    printf("\n%d > %d\nSvazannaya", z, u);
  }
  else{
    printf("\n%d < %d\nNe svazannaya", z, u);
  }
}
