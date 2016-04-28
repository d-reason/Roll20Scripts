Tracker-start (starts/pauses the tracker) 
!tj -start 

Tracker-reset (set, or reset the round count number) 
!tj -reset ?{round-start|1} 

Tracker-addstatus (adds a status) 
!tj -addstatus ?{name}:?{duration}:?{direction}:?{message} 

Tracker-editstatus (edit statues for selected tokens) 
!tj -edit 

Tracker-addfav (Add a favorite) 
!tj -addfav ?{name}:?{duration}:?{direction}:?{message} 

Tracker-listfavs (List your saved favorites) 
!tj -listfavs 


Functionality Summary:

Provides basic turn tracking behavior:
http://i.imgur.com/NRYEHJU.gif
In addition it has pausing support, allowing you to pause the tracker so the duration on statuses don't tick down. Or perhaps you wish to re-orient the turn order without affecting status durations currently in effect. Standard turn announcements as well as round announcements, closing the turn order automatically stops and clears the tracker for easy clean up.

Players can use the command !eot to advance their turn if they have control of the token.

Be aware:
The tracker graphic moves to the GM layer before shifting so from the player's perspective it simply vanishes and appears again whenever the token moves or a turn advances. This was done to prevent players from following the graphic to reveal the position of enemies that are perhaps behind a light wall or within the FOW. If this enemy however is on the GM layer, it's a moot point since the tracker will be hidden as well, but it's useful for tactical combat that doesn't involve moving tokens between layers that don't need to be. Also if the enemy is close to a thin wall, they could probably still see the outline of the spinning tracker.

Be aware:
If you delete the current turn token (the head of the tracker), this will cause Roll20 to miss some updates in regards to the turn order. What will occur is the tracker won't move or update as internally the turn order on the campaign hasn't updated despite what you see on your end as a client. To avoid this, if you plan on removing a token at the head of the tracker, delete it from the turn order first before deleting the actual token to allow it to advance. If you find yourself caught having deleted the current turn's token (the head), then you'll need to advance the turn order forcing a double update to occur from Roll20. You can pause the tracker and re-orient the tracker for the skipped turn. Note that this is only for the token at the top of the order, if you delete a token anywhere else in the turn order, there will be nothing amiss.

Allows multi-map turn tracking support:
http://i.imgur.com/8etVEYU.gif
The tracker can function across multiple maps for split parties! There is a minor graphical hiccup if you pause and unpause on different pages, but otherwise it functions as normal.

Tracks statuses:
http://i.imgur.com/KEdDyN3.gif
Easily tracks statuses, allowing you to create and add them on the fly. Markers are unique to each status, but it can also co-exist with other markers not used by any status until that marker is used by a status.

Status attributes:
Name: the name of the status. (global attribute)
Marker: the marker associated with this status, should be unique among the applied statuses. (global attribute)
Duration: the duration of the status. (always positive)
Direction: the tick rate of the duration each round the token's turn comes up. (positive or negative)
Message: Optional rider message describing the effect if needed, can include simple dice expressions. (leave blank for no value)

A special note about markers:
Markers are considered unique for each applied status. What this means is that the marker for say 'poisoned' cannot be the same marker for 'burning'. As you add statuses, it will inform you which markers are taken by which statuses. When you apply a favorite, it will refuse to apply the favorite, if the associated marker is already taken by an active effect.

A special note about direction:
The direction attribute is the 'tick rate per round' when the token's turn comes up of the duration. if the direction is set to 0, you have an infinite status and the duration becomes irrelevant (but the duration still needs to be >0 to prevent it from expiring). Infinite statuses are useful for durations you know will easily exceed the tactical round length (high level barkskin, bless, etc..) A positive number (+1,+2,1,2...) will increase the duration each tick which is useful for tracking rounds of rage used, or bardic performance and more. A negative number is the standard use-case for decreasing duration (-1,-2...).

Allows editing of statuses:
http://i.imgur.com/zzTJKcg.gif
Edit statues on the fly either by invoking the !tj -edit command or by clicking on the gear of the turn announcement.

Be aware:
When you edit global status attributes (the marker or the name) it will change for all tokens as reflects the status itself. Local attributes such as the message, duration, or direction are as stated, local. As to why this is, you can perhaps have a poison effect only do 1d2 strength damage which would mean one token would have a specific message, but the status across all the tokens would still be 'poison'.

Allows group editing of statuses:
http://i.imgur.com/pIReIjL.gif
Edit a status across multiple tokens.

Be aware:
When you edit local attributes across a group of tokens, each token could potentially have different values. For instance Shield of Faith from two separate clerics would clearly have different durations. When you edit a local attribute across a group of possibly disparate values, you set all of them to the new value irregardless of the local contents of each.

Uses a favorites system:
http://i.imgur.com/3lwuzOv.gif
The favorites system allows you to save statuses to use later. There is however only one unified list so if you 'bank' every status you want to use, you'll end up performing a dictionary look up each time you want to apply them. Think of this as a hot list for statuses you use often. 

Perhaps your party is facing a bunch of spiders in the next encounter, so adding a favorite for their venom would make the combat flow easier. When you find a status you're not using much any more, you can remove it from the favorites list.

A special note about favorites and their markers:
As mentioned in the notes about statuses, markers are unique to each applied status. Favorites can be considered 'cookie cutter' statuses so they're not 'applied' until you apply them. Take the scenario where you have a 'poison' status on several tokens already active, now you want to apply a status 'black widow venom' from your favorites. If they use the same marker as an active status (in this case 'poison'), it will alert, and prevent you from doing so.

A special note about editing and applying favorites:
Favorites, being 'cookie cutter' statuses are not influenced by edits to their statuses once applied. For instance, if I apply a 'dazed' favorite to a goblin, then select the goblin to edit its local status, that will not change the saved favorite's 'mold'.

A special note for power users:
If you want to create a macro to directly apply favorites, perhaps prompting a drop down as opposed to the graphical menu (maybe you want to categorize them by types such as a drop down for different poisons, or buffs, etc...), the favorites system internally uses the command
!tj -applyfav <favorite name>
which you can use for your macros.
