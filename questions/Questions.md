#questions
Here is a list of questions I organically ask in my research on effect systems. This will forever be a live document and new items will show up here as time goes by:
* [[Can effect systems simply be purely syntactic, with no user-defined handlers?]]
* [[Can there be an effect system but without a type system?]]
* [[Is it possible to just create an effect library without major refactors?]]

let a: number = 0

function no_state_allowed(arg: number): number | state  {
	a = 1; // in Koka, Eff, Effekt languages, compiler: side effect not handled
	// heap allocation is a side-effect
	
	return number * number
}

no_state_allowed();