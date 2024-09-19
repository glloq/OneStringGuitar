# OneStringGuitar

l'idée est de faire un systeme qui viend jouer d'un instrument a corde gratée de type guitare, basse etc 

l'objectif est de faire un test de plusieurs techniques pour jouer sur un instrument a une corde afin d'avoir une base adaptable jusqu'a 4 a 6 cordes dans l'avenir

## les choix techniques pour les accords

### servommoteurs
en utilisant un pca9685 nous pouvons facilement controller 16 servomoteurs

### solenoides
avec un mpc23017 et deuxs uln2803, nous pouvons controller 16 solenoides (500mA par solenoides max avec le uln2803) 

### moteurs pas a pas
avec un driver et un moteur pas a pas, on peut faire un reglage des positions via software.
on a deux facons de faire : 
avec un doigt toujour en appui   
![simple contact](https://github.com/glloq/OneStringGuitar/blob/main/img/simpleContact.png)

ou avec un systeme mecanique ou electromecanique pour deplacer le doigt sur un rail lineaire
![guide lineaire](https://github.com/glloq/OneStringGuitar/blob/main/img/guide%20lineaire.png)

## les choix techniques pour le grattage

## Servomoteur 
on peut utiliser un servomoteur pour gratter en direct ou en deporté en alternant entre 2 angles entre chaque grattage de la corde.
on peut aussi utiliser le servomoteur pour etoufer la note en remetant le pick contre la corde a la reception d'un message noteOff.
![grattage servo](https://github.com/glloq/OneStringGuitar/blob/main/img/grattage%20servo.png)

## Moteur 
on peut utiliser soit un moteur cc que l'on active pendant un certain temps soit utiliser un moteur pas a pas pour plus de precision (mais ca augmente le couts et la complexité) 

## solenoides

la technique la plus simple est d'utiliser deux solenoides opposé l'un a l'autre et d'alterner l'activation des deux solenoides pour gratter la corde.  
![grattage 2 solenoides](https://github.com/glloq/OneStringGuitar/blob/main/img/grattage%202%20solenoides.png)

on peut aussi utiliser un seul solenoide pour gratter la corde mais il faut utiliser un systeme mecanique qui complexifie le systeme afin d'eviter de gatter les corde 2 fois.


# la position des frettes

Pour déterminer les positions des frettes sur une corde d'un violoncelle en fonction de sa longueur, nous utilisons la règle des frettes, qui suit une division logarithmique. La position de chaque frette est calculée en utilisant la formule suivante :
 
d_n = L - (L / (2 ^ (n / 12)))

ou:
- `d_n` est la distance entre le sillet et la n-ième frette,
- `L` est la longueur vibrante de la corde (du sillet au chevalet),
- `n` est le numéro de la frette.

## Longueurs des Cordes Vibrantes pour Instruments à Cordes grattée

| Instrument         | Longueur de corde vibrante (en cm) |
|--------------------|------------------------------------|
| Guitare classique | 65 - 66                    |
| Guitare acoustique| 63 - 65                    |
| Guitare électrique| 62 - 64                    |
| Mandoline         | 35 - 40                    |
| Banjo             | 60 - 62                    |
| Ukulélé soprano   | 33 - 35                    |
| Ukulélé ténor     | 40 - 45                    |

