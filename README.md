# Backend System Design — Low-Level Design Practice

Two consumer systems modelled from scratch, with the UML committed alongside the
implementation.

## Why this repository exists

Low-level design is the interview round that cannot be crammed, because it asks
for judgement rather than recall: which entities exist, what each one owns, and
where behaviour belongs when the requirements change.

Reading about design patterns does not build that judgement. Modelling a system
somebody else already built — and then having to defend the class boundaries —
does. Each system here starts from the UML, so the structure is an argument that
can be reviewed before a single method is written.

## Systems

### Spotify — Music Player System

`Spotify MusicPlayerSystem/MusicPlayerApplication` · design: [`Spotify UML.pdf`](Spotify%20UML.pdf)

A music playback application modelled as a set of collaborating objects rather
than one controller class: playback control, playlist management, device
handling, and playback strategy each owning their own responsibility.

The interesting boundary is between *what* to play next and *how* playback
happens. Keeping selection strategy separate from the playback device is what
lets a new shuffle mode or a new output target be added without touching the
other.

### Zomato — Food Delivery System

`zomato/` · design: [`Zomato UML.png`](Zomato%20UML.png)

![Zomato UML](Zomato%20UML.png)

Restaurants, menus, carts and orders, with the ordering flow modelled end to
end — from browsing a menu through to a placed order.

The design question here is where the cart lives and who is allowed to mutate
it, because that boundary is what keeps pricing and availability consistent when
an order is being assembled.

## How to read this repository

Open the UML first, then the code. The diagram is the argument; the code is the
evidence that the argument holds together.

## Running it

<!-- Replace this block with the real commands once confirmed. -->

```bash
git clone https://github.com/mdhumayun7/Backend-System-design.git
cd Backend-System-design
```

## What this is not

- Not production systems. These are design exercises at the class level, with no
  persistence layer, no concurrency handling, and no API surface.
- Not a complete model of either product. Each covers the core domain only —
  enough to make the class boundaries meaningful, and no further.
- Class diagrams only so far; sequence diagrams for the main flows are still to
  be added.

## Roadmap

- Sequence diagrams for the primary flows in both systems
- A short written note per system explaining which pattern was chosen and what
  the alternative would have cost
- Unit tests covering the core domain objects
- Two more systems: a parking lot and a rate limiter

## Author

**MD Humayun** — M.Tech Computer Science (Information Security & Privacy), SVNIT Surat

[Portfolio](https://mdhumayun7.github.io/MD-HUMAYUN-PORTFOLIO/) ·
[GitHub](https://github.com/mdhumayun7) ·
[LinkedIn](https://www.linkedin.com/in/md-humayun-82051521a/)
