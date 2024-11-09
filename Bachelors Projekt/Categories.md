
## Word Equations
## Word Equations with regular constraints
## Word Equations with length constraints
## Word Equations + Full LIA

## Word Equations with regular constraints + length constraints
## Word Equations with regular constraints + Full LIA
## Word Equations with transducers



# String functions
- Concatenation (str.++ $s_1$ $s_2$)
- Length (str.len $s$)
- Lexicographic Ordering (str.< $s_1$ $s_2$)
- Lexicographic Reflexive Closure (str.<= $s_1$ $s_2$)
- Substring Access (str.at $s$ $i$) (str.substr $s$ $i$ $n$)

## String Relationships
- (str.prefixof $p$ $s$)
- (str.suffixof $p$ $s$)
- (str.contains $s_1$ $s_2$)

## String Replacement
- (str.replace_re $s$ $r$ $s_3$)
- (str.replace_re_all $s$ $r$ $s_3$)

## Conversion Functions
- (str.to_code $s$)
- (str.from_code $n$)
- (str.to_int $s$)
- (str.from_int $n$)

## Digit Check
- (str.is_digit $s$)

# Regular Expression Functions
## Constants
- (re.none)
- (re.all)
- (re.allchar)

## Operations
- (re.++ $r_1$ $r_2$)
- (re.union $r_1$ $r_2$)
- (re.inter $r_1$ $r_2$)
- (re.* $r$)
- (re.+ $r$)
- (re.comp $r$)
- (re.diff $r_1$ $r_2$)

## Membership
- (str.in_re $s$ $r$)

## Special Constructions
- (str.to_re $s$ $r$)
- (re.opt $r$)

## Powers and Loops
- ((_ re.^ $n$) r)
- ((_ re.loop $n_1$, $n_2$) $r$)