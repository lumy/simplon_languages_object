
# Subject

Inspired (copy) from EPITECH https://github.com/GwendolineRodriguez/Epitech/blob/master/CppPool/Subjects/Rushs/rush2.pdf

You should write a software in the languages of your choice (not python thought)
Your languages might not implement all design pattern asked in the subject (javascript doesn't
implement Interface), in this case you'll have to adapt your code to be as close as possible as the
subject but you're free to adapt the subject in this case.
You don't have to finish the subject, by if you start it, try to go as far as possible and ask
questions !

## SANTA’SELVES

Santa Claus has made an official request for your school to systemize his gift wrapping chain.
He is tired of all these stupid elves and would like to make the whole process auto-matic.
He demands that you design a chain packaging simulator.

> This subject is deliberately opaque. You must reorganize things logically and deduce the implied
> instructions to meet all requirements. Reading the subject ENTIRELY is necessary to understand all
> the interactions between the various elements. And if you’re asking, no! Koalas don’t smoke
> eucalyptus before they write a subject!

## Toys

Santa has given you a list describing what was, up until now, done by the elves on the gift wrapping
production chain.
Your project leader has taken care of the functional analysis,as well as most of the design for you.
He provides you with a list of indications and constraints to implement the different parts of the
simulator:
  - A `Teddy` is a Toy
  - A `LittlePony` is also a Toy
  - A `Teddy` screams "gra hu" when picked up (through the `isTaken` method)
  - A `LittlePony` screams "yo man" when picked up (through the `isTaken` method)
  - A `Toy` is an Object

You should also write unittest:
The unittest must make sure it is possible to create a LittlePony with "happypony" as its title, and
a Teddy titled "cuddles".


## A box Story

Now that you have toys, it’s time to take care of wrapping gifts:
  - A `Box` is a `Wrap`
  - A `GiftPaper` is also a  `Wrap`
  - Elves wrap gifts via a `Wrap`’s `wrapMeThat` method
  - Elves must be able to put an Object (and only one!) into a `Box` by wrapping it into the
    `Box`,but only if the `Box` is open
  - A closed `Box` cannot wrap
  - A `GiftPaper` doesn’t have to be open to wrap
  - A `Wrap` which already contains an Object cannot wrap anymore
  - Elves can open a `Wrap` to access the contained Object, through the `Wrap`’s `openMe` method
  - Once a `Wrap` is open and the object has been taken by an Elf,the `Wrap` is empty once again and
    can wrap a new Object
  - Elves can close open Boxes, through the Wrap’s `closeMe` method
  - When elves take a `Wrap`,they say "whistles while working"
  - When elves wrap objects, they say "tuuuut tuuut tuut"

The team leader demands that you implement the `Wrap`, `Box` and `GiftPaper` classes.
You must also implement unittest: It should put a `Toy` (like a `Teddy`) into a `Box` and the Box
into a `GiftPaper`.

Error cases must generate explicit messages on the error output.
Of course,feel free to add any additional tests you need.

# Convoyer Belt

Time to add a workstation:
  - Elves have a `Table` in front of them, and a `ConveyorBelt` by their side
  - Nothing can be put on the `ConveyorBelt` if there is already something on it
  - Elves can put and take any Object on the `Table` or the `ConveyorBelt`
  - When there is no more room on the `Table`, it collapses. It can hold up to 10 Objects
  - Elves receive `Wraps` by pressing the "IN" button of the `ConveyorBelt` using their Hand
  - Elves send what’s on the `ConveyorBelt` to Santa by pressing its "OUT" button
  - A `Wrap` sent to Santa vanishes, meaning there is once again space on the `ConveyorBelt`
  - Elves can look at the `Table` to see what’s on it. In return,they get an array of the titles of
    the various Objects.
  - Pushing a button of the `ConveyorBelt` when the input/output hasn’t been initialized yet is an
    error.

The project leader insists that you must write the `ITable` and `IConveyorBelt` interfaces, as well
as the `PapaXmasTable` and `PapaXmasConveyorBelt` classes implementing those interfaces.
Santa’s table and conveyorbelt have everything required to make 2 gifts. The
organization/distribution of wraps/toys between the conveyorbelt and the table is up to you.
You must also provide the following functions:
  `ITable *createTable();`
  `IConveyorBelt *createConveyorBelt();`

These functions let clients reify(instantiate) the two objects.
The error cases must generate explicit messages on the error output.


# A job for an elf

It is now time to simulate the actual job of the elves.
Create an `IElf` interface, describing all the actions elves may do.
These were all specified through out the subject. Once that’s done, implement the `PapaXmasElf`
class, implementing the interface.
When an elf is told to wrap a gift, it does so all by itself, using the `Table` and `ConveyorBelt`
to wrap up a gift and send it by pressing the `ConveyorBelt`’s OUT button.

# The Boxes

Let’s complicate things a little.
Implement the `TableRand` and `ConveyorBeltRand` classes, that provide a random set of `Objects`.
Your Elf must be able to make as many presents as possible using these Objects, and send them to
Santa.
When it can’t do anything anymore, it yells: `o’pa ere’s somin’ wron’ in da box!` Oh, by the way,
there’s something really weird with the `ConveyorBeltRand`. It makes a lot of noise.
The goblin mechanic that delivered it said it talks.
More specifically, he said `espeex’n’XML`.
Ruddy goblin accents, I never understand’em. The fact of the matter is, your `ConveyorBeltRand` must
`speex’n’XML`: it must describe the gift it is sending, from the outside in,inXML.
The goblin says it’s something called `serialization`,for what it’s worth.

# IS SANTA QUANTUM?

It is now time to implement SantaClaus, as a separate program. Santa is lazy, and simply waits for
gifts to put them into the sleigh.
A gift is the result of an `XMLserialization` of your objects. These, stored in files, are passed as
parameters to Santa on the commandline:`./santa gift1.xml gift2.xml gift3.xml` You will have to show
the inspector that your Santa loads each gift from XML into memory using what the ol’goblin called
`deserialization`. To do so, you must take each gift, open it, take the toy inside it and put it
back into the box. Quality control is very important for Santa: to know wether Shrodinger’s cat is
still alive, he simply opens the box! When he takes the toy out of the box, it yells (useful tok
know what’s inside, right?).


# THE WARP MACHINE OR ONE MORE STEP TOWARDS DEMENTIA

Gifts are coming out of a device called the Warp Machine.
Any gift sent by the new `ConveyorBelt` with the OUT button is received by the warp machine, through
one of these parts that look like a big magic sock. This sacred machine expects a mystical number
before it connects to the elves’magical `conveyorbelt`, number provided by Santa when it is launchin
warp mode with the `-w` flag (as in “WarpMeUpScotty”). There is an old saying among the dwarves,
which goes something like this:

> To connect the magical sock to the warp, this sock must be "figurated in ’u di pee multi-caste!?".
> The mystical number works by quadruplet. The first one always starts between 234 and 239. Ask my
> cousin gougle for more information.

I didn’t say it was a nice saying. Just an old one.
Anyways. Modify your `SantaClaus` program so that it takes this mystical number as parameter and
properly configures the warp machine connected with the magic sock.
In addition, the goblin mechanic made a new version of `ConveyorBeltRand`: the `MagicalCarpet`.
Just like the `ConveyorBeltRand`, "espeex’n’XML", and the noise it produces is sent out into the
warp.
The XML is then captured by Santa’s sock. This lets Santa know what’s going on on the
`ConveyorBelt`. He can then get the gift out of the wrap, and proves everything worked correctly to
the inspector by grabbing the toy inside it.
This means many elf production lines can all send their gifts to Santa at the same time!
If several Santa's use the same mystical number, they will all receive the gifts destined to this
number,
which is very convenient for duplicating gifts. Several SantaClaus ? We told you he was quantum!
Pay attention!

Bonus: get together with other groups and use the same `XMLelements`. This will make it possible for
your elf production lines to work with their Santas, and vice versa!
