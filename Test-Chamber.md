### Test Chamber

Originally built just to be able to visualize the existing NAL8 examples, it is now our most complex application example, there you can built arbitrary logic circuits, combine doors and lights with switches, create machines which produce pizza, build arbitrary mazes the system has to solve on the fly, where the structure of the circuits are not known to NARS (if not especially told). This example will one day show the difference between narrow AI and general AI very clearly, and already now is a source of very interesting results.

**The Elements of TestChamber in the left window from top to bottom:**

* Structural: Place walls, floors, or water

* Logic: Build logic circuits

* Machine: Add things like lights, doors etc.

**Force Action: Force NARS to do something.**

* "Go-To named" will make NARS go to a clicked place.

* "Pick named" will make NARS pick an object, for example a key.

* "Activate switch" will make it activate a switch.

* "Deactivate switch" deactivates it.

* perceive/name lets you define new places, you can let NARS go there with "Go-To named" or force the goal "be somewhere" on it in which case NARS will try to get there whatever it involves to make this possible.

**Request Goal: Force NARS to desire something.**

* try things will desire applying its actions on different things, which keeps it active. (Since desires like visiting switches will develop anyway, this is not needed after some training, at least if tell object categories is enabled)

* be somewhere: let NARS desire to be somewhere

* hold something: let NARS desire to pick up something, like for example a key

* make switched on: let NARS desire to make a light or a switch switched on

* make switched off: same for off

* make opened: let NARS desire to open a door

* make closed: same for closing

* be chatty: let NARS gain some defined experience in which case it will get desire to apply the say operator in different situations. (experimental, but works, communication as a desire, see more in: [NaturalLanguageProcessing](https://github.com/opennars/opennars/wiki/Natural-Language-Processing) wiki page)

Predefine knowledge: Contains some knowledge one can tell it about, like for example common sense in which case it will have evidence that it is somewhere after it goes there, that it holds something after it picks it, made to speed up learning a bit.

Need of resources: if "need pizza" is activated, a hunger goal will show up in NARS from time to time, which is only achievable by eating pizza which can be placed.

**Advanced Settings:**

* Allow joy in action inserts forced actions as goal, in which case they will gain desire of forced actions directly, which distracts NARS from doing what you want often as consequence, but allows it to like repeating what it was forced to do. Don't allow joy deactivates this mode.

* Tell object categories will suggest a category to objects which get placed, like when {key0} is placed, NARS will get the information <{key0} --> key>, what this means NARS needs to find out, but it helps NARS to categorize keys together for example, and not just objects by what actions leaded to what changes in the environment (in which case NARS would develop its own concept of key, but this can happen despite the given information, but the similarity of the own concept to key will likely be recognized)

* Load/Save: Save the state of TestChamber into a file, or load examples we provided.

![testchamber](https://cloud.githubusercontent.com/assets/11791925/6994213/5a8a3f5e-db43-11e4-8097-fe40c33d5f2b.png)