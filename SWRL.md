# SWRL
## Details
* Category: [Standards](../categories/Standards.md)
* Module Prerequisites: [SPARQL](../modules/SPARQL.md)
* Audience: [Student, Developer](../audiences/Student,_Developer.md)
* Level: [Intermediate](../levels/Intermediate.md)

## Content


#### What is SWRL ?

SWRL stands for Semantic Web Rule Language, a rule-based language proposed to combine structured world of ontologies and inferential capabilities of rule-based reasoning. It is a conjunction of OWL 2 DL with a subset of RuleML, applying rules of datalog/RuleML onto OWL ontologies. It acts more like a complement to the knowledge represented in ontologies for more expressive semantic reasoning.

#### What was the need for SWRL ?

Even with various powerful data modelling and knowledge representation standards such as RDF, RDFS, OWL being present, some key aspects like expressivity, inference or automated reasoning, specifying complex logical rules lacked accessibility. While OWL is excellent for ontology modelling, representing taxonomies and establishing relationships, due to absence of rule-based approach, it cannot perform inference or specific decision-making logic based on conditions. As a result, SWRL (a W3C Member Submission in May 2004) emerged to derive new knowledge or make logical deductions based on the existing RDF data & providing higher degree of expressiveness.

#### SWRL Syntax

SWRL rules are typically an implication between an antecedent (body) and consequent (head). This can be interpreted as: whenever the conditions specified in the antecedent hold, then the conditions specified in the consequent must also hold [1].
a human readable syntax rule has the form:

    antecedent (body) ⇒ consequent (head)

where both antecedent and consequent are conjunctions of atoms (assertions) which can contain a combination of OWL constructs, written a1 ∧ ... ∧ an. 
Variables are indicated using the standard convention of prefixing them with a question mark (e.g., ?x)

##### Example1:

    hasParent(?x,?y) ∧ hasBrother(?y,?z) ⇒ hasUncle(?x,?z)

For example, "If X has a parent of Y and Y has a brother of Z, then it infers that X has an uncle of Z."

#### SWRL Semantics

The constructs of atoms can either be in the form of OWL-DL class descriptions, individual-valued properties, data-valued properties, OWL same individuals, OWL different individuals, or the specific built-in functions.

        | C(i) | R(i, j) | D(v) | U(i,v) | builtIn(p, v1,…,vn) | i = j | i ≠ j |

C = Class						
D = Data type
R = Object Property					
U = Data type Property
i, j = Object variable names or Object individual names
v1,…, vn = Data type variable names or Data type value names
p = Built-in names

SWRL atoms in the antecedent (body) are satisfied,
•	if it is empty (trivially true)
•	or every atom of it is satisfied
SWRL atom in the consequent (head) is satisfied,
•	if it is not empty
•	and it is satisfied
A rule is satisfied by an interpretation of ‘I’ iff every binding B(I) that satisfies the antecedent B(I) satisfies the consequent
Using this syntax, a rule asserting that the composition of parent and brother properties implies the uncle property can be written as:

#### Example2: 
        person(?x) ∧ hasAge(?x, ?age) ∧ swrlb:greaterThan(?age, 18) → adult(?x)














## Related KGC Media
* Workshop Example
* Tutorial Example

## References
[1] Reference example.

## Contributors
* Cogan Shimizu
