# OneStringGuitar

l'idée est de faire un systeme qui viend jouer d'un instrument a corde gratée de type guitare, basse etc 

l'objectif est de faire un test de plusieurs techniques pour jouer sur un instrument a une corde afin d'avoir une base adaptable jusqu'a 4 ou 6 cordes dans l'avenir

# les choix techniques 

## solenoides
avec des mpc23017 et deux uln2803, nous pouvons controller 16 solenoides par mcp (500mA par solenoides max avec le uln2803) 
### accords
il faut placer des systemes de doigts entre les frettes qui viendrons tirer la corde vers le manche et faire l'accord voulu. 
il faudra absolument penser a utiliser des systeme pour amortir les deplacement ON/OFF de chaque solenoide pour limiter les bruits mecanique (de la mousse/tissus ou encore adapter la tension d'alimentation)   
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/fingers%20solenoides.png" alt="Your image title" width=100% height=100%/>
### grattage 
la technique la plus simple est d'utiliser deux solenoides opposé l'un a l'autre et d'alterner l'activation des deux solenoides pour gratter la corde.   
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/grattage%202%20solenoides.png" alt="grattage 2 solenoides" width=100% height=100%/>

## servommoteurs
### accords
en utilisant des pca9685 nous pouvons facilement controller 16 servomoteurs, nous pouvons utiliser la meme methode qu'avec des solenoides sans les systeme d'amortissement.
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/fingers%20servo.png" alt="Your image title" width=100% height=100%/>
### grattage 
on peut utiliser un servomoteur pour gratter en direct ou en deporté en alternant entre 2 angles entre chaque grattage de la corde.
on peut aussi utiliser le servomoteur pour etoufer la note en remetant le pick contre la corde a la reception d'un message noteOff.   
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/grattage%20servo.png" alt="grattage servo" width=100% height=100%/>
## moteurs pas a pas
avec un driver et un moteur pas a pas, on peut faire un reglage des positions via software.
on a deux facons de faire : 
avec un doigt toujour en appui 
<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/simpleContact.png" alt="Your image title" width=100% height=100%/>

ou avec un systeme mecanique ou electromecanique pour decendre le doigt sur un rail lineaire  

<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/guide%20lineaire.png" alt="Your image title" width=100% height=100%/>

dans ce cas nous pouvons utiliser un systeme actioné via un servomoteur ou un solenoide directement sur le patin du rail lineaire ou deporté en fixe (pour eviter des cables electrique en mouvements et augmenter la fiabilité) 

<img src="https://github.com/glloq/OneStringGuitar/blob/main/img/bowden.png" alt="bowden" width=100% height=100%/>

# les differentes version de code possible

il est plus simple de combiner les meme type d'actionneurs (solenoides ou servomoteurs) afin d'avoir le meme temps de reaction entre l'accord et le grattage.

ca nous donne donc 3 familles de codes à faire :
- utiliser des solenoides
- utiliser des servomoteurs
- utilser des moteurs pas à pas
  - sans actionneur
  - avec un servomoteur pour descendre le doigts
  - avec un solenoide pour descendre le doigts

les solenoides :
- la solution avec le moins delais 
- revient cher avec le cout des solenoides
- relativement bruyant et chauffe => il faut isoler les bruits mecanique et utiliser un systeme de dissipation de la chaleur
  
les servomoteurs :
- delais d'action assez elevée
- prend plus de place
- le plus simple a coder
    
le moteur pas a pas :
- la solution la plus simple a adapter
- le plus gros delais d'action ( et variable en fct de la distance ?) 







