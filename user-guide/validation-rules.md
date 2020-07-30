# Validation Rules

**\(UML001\) Name expected.**

* Element should have a name.
* Applies to: `UMLModelElement`.
* Exceptions: `UMLParameter (only if direction === 'return')`, `UMLDirectedRelationship`, `UMLRelationshipEnd`, `UMLUndirectedRelationship`, `UMLAssociationClassLink`, `UMLRegion`, `UMLPseudostate`, `UMLFinalState`, `UMLControlNode`, `UMLEndpoint`, `UMLGate`, `UMLImage`.

**\(UML002\) Name is already defined.**

* If element has a name, then it should be unique in the namespace.
* Applies to: `UMLModelElement`.
* Exceptions: `UMLOperation`.

**\(UML003\) Conflict with inherited attributes.**

* Applies to: `UMLAttribute`.

**\(UML004\) Signature conflict.**

* Same signature is not allowed in a classifier.
* Applies To: `UMLOperation`.

**\(UML006\) Final and leaf element must not have child.**

* If `isFinalSpecifiction` or `isLeaf` is true, then it should not have child.
* Applies to: `UMLClassifier`.

**\(UML007\) Duplicated generalizations.**

* Do not make duplicated generalizations from the same element.
* Applies to: `UMLClassifier`.

**\(UML008\) Circular generalizations.**

* Do not generalize from one of the children.
* Applies to: `UMLClassifier`.

**\(UML009\) Duplicated realizations.**

* Applies to: `UMLClassifier`.

**\(UML010\) Duplicated role names of associated classifiers.**

* Applies to: `UMLClassifier`.

**\(UML011\) All attributes and operations of interface must be public.**

* All attributes and operations of an interface should have public visibility.
* Applies to: `UMLInterface`.

**\(UML012\) Aggregation must be one in an association.**

* Applies to: `UMLAssociation`.

**\(UML013\) Type of an artifact instance must be an artifact.**

* Applies to: `UMLArtifactInstance`.

**\(UML014\) Type of a component instance must be a component.**

* Applies to: `UMLComponentInstance`.

**\(UML015\) Type of a node instance must be a node.**

* Applies to: `UMLNodeInstance`.

**\(UML016\) A metaclass must have name defined in metamodel.**

* Applies to: `UMLMetaClass`

**\(UML017\) A stereotype must inherits from stereotype.**

* Applies To: `UMLStereotype`

**\(UML018\) A stereotype must contained by a profile.**

* Applies To: `UMLStereotype`

**\(UML019\) An actor only can associate with use cases, components, and classes.**

* Applies To: `UMLActor`

**\(UML020\) A use case cannot include use cases that directly or indirectly include it.**

* Applies To: `UMLUseCase`

**\(UML021\) An initial vertex can have at most one outgoing transition.**

* Applies To: `UMLPseudostate (kind = 'initial')`

**\(UML022\) The outgoing transition from an initial vertex must not have a trigger or guard.**

* Applies To: `UMLPseudostate (kind = 'initial')`

**\(UML023\) History vertices can have at most one outgoing transition.**

* Applies To: `UMLPseudostate (kind = 'deepHistory' | 'shallowHistory'`

**\(UML024\) A join vertex must have at least two incoming transitions and exactly one outgoing transition.**

* Applies To: `UMLPseudostate (kind = 'join')`

**\(UML025\) A fork vertex must have at least two outgoing transitions and exactly one incoming transition.**

* Applies To: `UMLPseudostate (kind = 'fork')`

**\(UML026\) A junction vertex must have at least one incoming and one outgoing transition.**

* Applies To: `UMLPseudostate (kind = 'junction')`

**\(UML027\) A choice vertex must have at least one incoming and one outgoing transition.**

* Applies To: `UMLPseudostate (kind = 'choice')`

**\(UML028\) Only submachine states can have connection point references.**

* Applies To: `UMLState`

**\(UML029\) A state is not allowed to have both a submachine and regions.**

* Applies To: `UMLState`

**\(UML030\) A region can have at most one initial vertex.**

* Applies To: `UMLRegion`

**\(UML031\) A region can have at most one deep history vertex.**

* Applies To: `UMLRegion`

**\(UML032\) A region can have at most one shallow history vertex.**

* Applies To: `UMLRegion`

**\(UML033\) A final state cannot have any outgoing transitions.**

* Applies To: `UMLFinalState`

**\(UML034\) A final state cannot have regions.**

* Applies To: `UMLFinalState`

**\(UML035\) A final state cannot reference a submachine.**

* Applies To: `UMLFinalState`

**\(UML036\) A final state has no entry behavior.**

* Applies To: `UMLFinalState`

**\(UML037\) A final state has no exit behavior.**

* Applies To: `UMLFinalState`

**\(UML038\) A final state has no state \(doActivity\) behavior.**

* Applies To: `UMLFinalState`

**\(UML039\) A fork segment must not have guards or triggers.**

* Applies To: `UMLTransition`

**\(UML040\) A join segment must not have guards or triggers.**

* Applies To: `UMLTransition`

**\(UML041\) A fork segment must always target a state.**

* Applies To: `UMLTransition`

**\(UML042\) A join segment must always originate from a state.**

* Applies To: `UMLTransition`

**\(UML043\) Transitions outgoing pseudostates may not have a trigger \(except for those coming out of the initial pseudostate\).**

* Applies To: `UMLTransition`

**\(UML044\) The classifier context of a state machine cannot be an interface.**

* Applies To: `UMLStateMachine`

**\(UML045\) A decision node has one or two incoming edges and at least one outgoing edge.**

\_ Applies To: `UMLDecisionNode`

**\(UML046\) A merge node has one outgoing edge.**

* Applies To: `UMLMergeNode`

**\(UML047\) The edges coming into and out of a merge node must be either all object flows or all control flows.**

* Applies To: `UMLMergeNode`

**\(UML048\) An initial node has no incoming edges.**

* Applies To: `UMLInitialNode`

**\(UML049\) Only control edges can have initial nodes as source.**

* Applies To: `UMLInitialNode`

**\(UML050\) A final node has no outgoing edges.**

* Applies To: `UMLFinalNode`

**\(UML051\) A fork node has one incoming edge.**

* Applies To: `UMLForkNode`

**\(UML052\) The edges coming into and out of a fork node must be either all object flows or all control flows.**

* Applies To: `UMLForkNode`

**\(UML053\) A join node has one outgoing edge.**

* Applies To: `UMLJoinNode`

**\(UML054\) The edges coming into and out of a join node must be either all object flows or all control flows.**

* Applies To: `UMLJoinNode`

**\(UML055\) All edges coming into or going out of object nodes must be object flow edges.**

* Applies To: `UMLObjectNode`

**\(UML056\) Control flows may not have object nodes at either end, except for object nodes with control type.**

* Applies To: `UMLControlFlow`

**\(UML057\) Object flows may not have actions at either end.**

* Applies To: `UMLObjectFlow`

