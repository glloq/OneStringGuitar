# OneStringGuitar

l'idée est de faire un systeme qui viend jouer d'un instrument a corde gratée (ukulele, guitare, basse, etc ...) depuis des messages midi.

l'objectif ici est de faire une liste de plusieurs techniques pour jouer sur un instrument a une corde afin d'avoir une base adaptable jusqu'a 4 ou 6 cordes dans l'avenir.


# les choix techniques 

## solenoides
avec des mpc23017 et deux uln2803, nous pouvons controller 16 solenoides par mcp (500mA par solenoides max avec le uln2803) 
### accords
il faut placer des systemes de doigts entre les frettes qui viendrons tirer la corde vers le manche et faire l'accord voulu. 
il faudra absolument penser a utiliser des systeme pour amortir les deplacement ON/OFF de chaque solenoide pour limiter les bruits mecanique (de la mousse/tissus ou encore adapter la tension d'alimentation)   
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/fingers%20solenoides.png" alt="Your image title" width=80% height=80%/>

### grattage 
la technique la plus simple est d'utiliser deux solenoides opposé l'un a l'autre et d'alterner l'activation des deux solenoides pour gratter la corde.   
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/grattage%202%20solenoides.png" alt="grattage 2 solenoides" width=80% height=80%/>
une fois le solenoide de grattage desactivé le pick vient contre la corde pour etouffer la note.

-----------------------------------------------------------------
## servommoteurs
### accords
nous pouvons utiliser la meme methode qu'avec des solenoides sans les systeme d'amortissement.
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/fingers%20servo.png" alt="Your image title" width=80% height=80%/>
### grattage 
on peut utiliser un servomoteur pour gratter en direct ou en deporté en alternant entre 2 angles entre chaque grattage de la corde.
on peut aussi utiliser le servomoteur pour etoufer la note en remetant le pick contre la corde a la reception d'un message noteOff.   
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/grattage%20servo.png" alt="grattage servo" width=60% height=60%/>

-----------------------------------------------------------------
## moteurs pas a pas
avec un driver et un moteur pas a pas, on peut faire un reglage des positions via software.
### accords
on a deux facons de faire : 
Avec un doigt toujours en appui :
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/simpleContact.png" alt="Your image title" width=80% height=80%/>
ou avec un systeme mecanique ou electromecanique pour decendre le doigt sur un rail lineaire  ou autre mecanisme de translation
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/guide%20lineaire.png" alt="Your image title" width=80% height=80%/>
dans ce cas nous pouvons utiliser un systeme actioné via un servomoteur ou un solenoide directement sur le patin du rail lineaire ou deporté en fixe (pour eviter des cables electrique en mouvements et augmenter la fiabilité) 
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/bowden.png" alt="bowden" width=80% height=80%/>
### grattage 
on peut tuiliser des solenoides ou des servomoteurs en fonction 

# les differentes version de code possible

il y a donc plusieurs familles de code a faire, je vais ajouter les liens vers chaque repo qui contient les details technique de chaque solution
- utiliser des solenoides
- utiliser des servomoteurs
- utilser des moteurs pas à pas
  - sans actionneur
  - avec servomoteurs
  - avec solenoides







