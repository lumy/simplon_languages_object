
# Subject

Inspired (copy) from EPITECH https://github.com/GwendolineRodriguez/Epitech/blob/master/CppPool/Subjects/Rushs/rush2.pdf

You should write a software in the languages of your choice (not python thought)
Your languages might not implement all design pattern asked in the subject (javascript doesn't
implement Interface), in this case you'll have to adapt your code to be as close as possible as the
subject but you're free to adapt the subject in this case.

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
