# Lindenmayer_Systems
followed a tutorial

# Lindenmayer Systems (L-Systems)

Aristid Lindenmayer was a Hungarian biologist who lived from 1925 to 1989. He developed the idea of the L-system in 1968 where the "system" is a set of rules, applied to a string (referred to as the axiom). The nature of the system is recursive, so fractals can be generated. Using his L-systems, he was able to model the behavior of cells of plants. 

> L-systems nowadays are used to model whole plants

---

## Simple Example of an L-system

    "A" - initial string (or axiom)

**Rules:**

     character 'A' is replaced by 'AB'
     character 'B' is replaced by 'A'

**Results after applying rules:**

$$i = 0 ⟶ \text{'A'}$$

$$i = 1 ⟶ \text{'AB'}$$

$$i = 2 ⟶ \text{'ABA'}$$

$$i = 3 ⟶ \text{'ABAAB'}$$

$$i = 4 ⟶ \text{'ABAABABA'}$$

$$i = 5 ⟶ \text{'ABAABABAAABAAB'}$$

$$i = 6 ⟶ \text{'ABAABABAABAABABABABA'}$$

---

## L-system for modeling honeycombs

    alphabet: A, B
    constants: not available
    axiom: A
    rules: (A ⟹ AB), (B ⟹ A)

**Interpreting alphabetic characters as commands:**

"A" $→$ rotate $60$&deg;, forward $1$

"B" $→$ rotate $-60$&deg;, forward $1$

---

## L-system for Sierpinski Triangle

    alphabet: "F", "G"
    constants: "+", "-"
    axiom: F
    rules: (F ⟹ F - G + F + G - F), (G ⟹ GG)
    angle: 120∘

**Interpreting alphabetic characters as commands:**

"F", "G" $→$ draw a segment
"+" $→$ turn right by angle
"-" $→$ turn left by angle

---

## Harter-Heighway Dragon

    alphabet: "X", "Y"
    constants: "F", "+", "-"
    axiom: FX
    rules: (X ⟹ X + YF+), (Y ⟹ -FX-Y)
    angle: 90° 

---

## Koch Snowflake

    alphabet: "F"
    constants: "+", "-"
    axiom: F++F++F
    rules: F ⟹ F-F++F-F

---

## Bracket L-systems and trees

### 1.)

    alphabet: "X", "F"
    constants: "+", "-", "[", "]"
    axiom: X
    rules: (X ⟹ F[+X]F[-X]+X), (F ⟹ FF)
    angle: 22.5° 

**Interpreting alphabetic characters as commands:**

"[" $→$ Save current positions and angle
"]" $→$ Restore position and angle values

### 2.)

    alphabet: "X", "F"
    constants: "+", "-", "[", "]", "@"
    axiom: X
    rules: X ⟹ F[@[-X]+X
    angle: random angle ∈ [0°, 45°]

**Interpreting alphabetic characters as commands:**

"@" $→$ Change : current color, thickness and length of segments

