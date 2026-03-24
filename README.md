# Fifa20
This analysis uses the FIFA 20 players dataset (players_20.csv)`18.3k player records with detailed physical, skill and contract attributes. The goal was to explore the data, cluster players by skill, and answer three focused questions about national origins, age vs. rating, and which attacking role is paid most.

The attributes used in the project are:

●	Name: Name of the player. 

●	Age: Age of the player.

●	Height: Height of the player in inches (transformed to centimeters in preprocessing).

●	Overall: General performance quality and value of the player representing the key positional skills and international reputation rated between 1-99. Overall attribute is used only in preprocessing and discussion stages because using it in modelling could lead to domination by this feature. The aim of the project is not basically sort and categorize the players using their overall talent and international reputation, but to cluster them based on using their whole skillset.

●	Potential: Maximum Overall rating expected to be reached by a player in the top of his career rated between 1-99.

●	PreferredFoot: Right or Left. Label encoder is applied as 0 for left and 1 for right.

●	WeakFoot: Represents how well a player uses his weak foot (e.g. left for righties) rated between 1 to 5.

●	WorkRate: Degree of the effort the player puts in terms of attack and defense rated as low, medium and high. This feature is divided into two new features as AttackWorkRate and DefenseWorkRate. Besides, label encoder is applied as 0 for low, 0.5 for medium and 1 for high.

●	Position: Position of the players on the pitch which determines their roles and responsibilities in the team. Forward positions in the football and FIFA 19 can be grouped as striker (ST: center striker, RS: right striker, LS: left striker), forward (CF: center forward, RF: right forward, LF: left forward) and winger (RW: right winger, LW: left winger). The word, forward, is used both as a general term and a special position. Strikers are positioned in front of forwards and wingers and very closed to the opposing goal. Their main responsibilities are attacking and scoring goals, that’s why their ball control, shooting and finishing skills are expected to be well. Center forwards are positioned right behind the strikers. They are expected to receive balls from the others and score assists to the others or goals. In addition to the skills expected from strikers, they have to be good at passing. Right forwards and left forwards are positioned at the right and left of the center forwards with the same expectations. Wingers are positioned near the touchlines to create chances for strikers and forwards from the right and left side of the field by breakthrough and crosses and to score goals. They are expected to be good at dribbling, acceleration, passing and crossing. Positions are used only in preprocessing and discussion stages. 

●	ST: Positional skill. Player’s general ability when playing in ST position rated between 1-99.

●	RS: Positional skill. Player’s general ability when playing in in RS position rated between 1-99.

●	LS: Positional skill. Player’s general ability when playing in in LS position rated between 1-99.

●	CF: Positional skill. Player’s general ability when playing in in CF position rated between 1-99.

●	RF: Positional skill. Player’s general ability when playing in in RF position rated between 1-99.

●	LF: Positional skill. Player’s general ability when playing in in LF position rated between 1-99.

●	RW: Positional skill. Player’s general ability when playing in in RW position rated between 1-99.

●	LW: Positional skill. Player’s general ability when playing in in LW position rated between 1-99.

●	Crossing: Crossing skill of the player rated between 1-99. Cross is a long-range pass from wings to center.

●	Finishing: Finishing skill of the player rated between 1-99. Finishing in football refers to finish an attack by scoring a goal.

●	HeadingAccuracy: Player’s accuracy to pass or shoot by using his head rated between 1-99.

●	ShortPassing: Player’s accuracy for short passes rated between 1-99.

●	LongPassing: Player’s accuracy for long passes rated between 1-99.

●	Dribbling: Dribbling skill of the player rated between 1-99. Dribbling is carrying the ball without losing while moving in one particular direction.

●	SprintSpeed: Speed rate of the player rated between 1-99.

●	Acceleration: Shows how fast a player can reach his maximum sprint speed rated between 1-99.

●	FKAccuracy: Player’s accuracy to score free kick goals rated between 1-99.

●	BallControl: Player’s ability to control the ball rated between 1-99.

●	Balance: Player’s ability to remain steady while running, carrying and controlling the ball rated between 1-99.

●	ShotPower: Player’s strength level of shooting the ball rated between 1-99.

●	Jumping: Player’s jumping skill rated between 1-99.

●	Penalties: Player’s accuracy to score goals from penalty rated between 1-99.

●	Strength: Physical strength of the player rated between 1-99.

●	Agility: Gracefulness and quickness of the player while controlling the ball rated between 1-99.

●	Reactions: Acting speed of the player to what happens in his environment rated between 1-99.

●	Aggression: Aggression level of the player while pushing, pulling and tackling rated between 1-99.

●	Positioning: Player’s ability to place himself in the right position to receive the ball or score goals rated between 1-99.

●	Vision: Player’s mental awareness about the other players in the team for passing rated between 1-99.

●	Volleys: Player’s ability to perform volleys rated between 1-99.

●	LongShots: Player’s accuracy of shoots from long distances rated between 1-99.

●	Stamina: Player’s ability to sustain his stamina level during the match rated between 1-99. Players with lower stamina get tired fast.

●	Composure: Player’s ability to control his calmness and frustration during the match rated between 1-99.

●	Curve: Player’s ability to curve the ball while passing or shooting rated between 1-99.

●	Interceptions: Player’s ability to intercept the ball while opposite team’s players are passing rated between 1-99. It is a defensive skill.

●	StandingTackle: Player’s ability to perform tackle (take the ball from the opposite player) while standing rated between 1-99. It is a defensive skill.

●	SlidingTackle: Player’s ability to perform tackle by sliding rated between 1-99. It is a defensive skill.

●	Marking: Player’s ability to apply strategies to prevent opposing team from taking the ball rated between 1-99. It is a defensive skill.  

Key findings (headline)
England, Germany and Spain supply the largest counts of players in this dataset.
Average player overall rises through the early 20s and peaks around age 32, after which itgenerally declines.

Strikers (ST), right wingers (RW) and left wingers (LW) share the same median weekly wage(€4,000), but RWs have the highest average and the single largest top wages — driven byelite stars (Messi as RW tops the list).

Clustering players by core skill attributes produces three broad archetypes that map well todefenders, midfielders and attackers.

Where the players come from — top nationalities

Insight

The dataset is concentrated in a handful of footballing nations; these countries produce themost players who appear in FIFA 20. Supporting data (top 10 nationalities) | nationality |count | |---|---:| | England | 1667 | | Germany | 1216 | | Spain | 1035 | | France | 984 | |Argentina | 886 | | Brazil | 824 | | Italy | 732 | | Colombia | 591 | | Japan | 453 | | Netherlands |416 |

England leads by a comfortable margin, with strong showings from Europe and SouthAmerica. This reflects large domestic leagues and scouting networks that feed the globalplayer pool represented here.

How rating changes with age — when do players stopimproving?

Insight

Average overall rating increases through early career and reaches its smoothed peak at age32 (mean overall ≈ 69.8 at peak). After that the smoothed trend generally declines.Supporting data (peak)

Peak age (smoothed mean): 32

Peak (smoothed) overall: ~69.8 

Players tend to develop through their late teens and 20s; the dataset’s smoothed meanindicates the highest typical performance around age 32. After that, the average rating falls— consistent with physical decline and role changes at older ages. Note that top eliteplayers can remain rated highly into their early/mid-30s, so the average peak reflects thewhole population rather than a few stars.

Which attacking role is paid most: ST, RW, or LW?

Insight

Median weekly wage is the same (€4,000) for LW, RW and ST, but RW has the highest meanand the single largest top wage; RW therefore dominates the top of the pay scale.Supporting data (summary by primary_position) | primary_position | count | median | mean |max | |---|---:|---:|---:|---:| | LW | 375 | 4000.0 | 14149.33 | 470000 | | RW | 367 | 4000.0 |15934.60 | 565000 | | ST | 2552 | 4000.0 | 10271.94 | 405000 |

Top earners by position (examples)

RW: L. Messi — FC Barcelona — overall 94 — wage €565,000/week

LW: E. Hazard — Real Madrid — overall 91 — wage €470,000/week

ST: Cristiano Ronaldo — Juventus — overall 93 — wage €405,000/week

Clustering players by skill — what archetypes emerge?

Insight

A clustering of outfield players on core skill attributes (pace, shooting, passing, dribbling,defending, physic and related sub-skills) found 3 useful clusters. 

These correspond broadlyto defenders, midfielders, and attackers. Supporting data (model selection and clusterprofiles)

Best number of clusters (k) by silhouette in the tested range: 3 (silhouette ≈ 0.215).

PCA 2-component explanation: PC1 ≈ 40.6%, PC2 ≈ 22.8% (≈63% total).

Cluster mean profiles (selected columns) | cluster | pace | shooting | passing | dribbling |defending | physic | overall | potential | wage_eur | age | |---:|--
-:|---:|---:|---:|---:|---:|---:|---:|---:|---:| | 0 | 60.8 | 36.0 | 48.7 | 52.1 | 61.8 | 67.4 | 63.6 | 69.9 | 4,893.5 | 24.6 | | 1 | 70.0 | 60.8 |66.7 | 69.9 | 59.2 | 69.2 | 71.4 | 74.2 | 18,755.8 | 27.1 | | 2 | 71.8 | 58.5 | 54.9 | 64.4 | 32.9 | 57.5 |63.5 | 70.7 | 4,432.9 | 23.5 |

Most common positions per cluster:

Cluster 0 — largely defenders (CB, RB, LB, CDM, CM)

Cluster 1 — midfield group (CM, CDM, LB/RB, also some ST)

Cluster 2 — attacking group (ST, RM, LM, CAM, CM)

Quick report-style takeaways from the general visuals

Distributions

overall and potential are unimodal and fairly concentrated (ratings systems tend to do that), while wage_eur and value_eur are extremely heavy-tailed, which is 

why the log-scale histograms are much more readable.

Correlations with wages (strongest)

Looking at correlations among selected numeric columns, the strongest drivers of wage_eur are:

•	value_eur about 0.86 (very strong)

•	overall about 0.57

•	potential about 0.48 Then technical skills like passing (0.40) and dribbling (0.37) show meaningful relationships too.
That matches what you’d expect: wages follow market value and overall quality, then separate further based on elite “on-ball” skill.

