##1a)
                  
### Axioms 	


	
\_____________________________

a in Aobjects


\_____________________________

v in Vobjects




### inference rule   

x in Vobjects

\---------------

x in Aobjects



###inference of expression    

x in Aobjects   y in Aobjects

\-----------------------------

x & y in Aobjects


##1b)

The grammar in the previous section is ambiguous because we can create a single string

multiple ways.  For example, the string baab can be created the following ways.


					 A                               A
				   /   \                           /   \
                  A  &  A          OR             A  &  A
                 /     / \                       / \    |
                 b    A & A                     A & A   b
                 |    |   /\                    |  / \  |
                 b    a   a b                   b a  a  b 


##1c)

S produces either A, B, or C

A produces either a and A, or simply a

B produces either b and B, or epsilon (terminal)

C produces either c and C, or simply c


##1d)

S::= AaBb

A::= Ab|b

B::= aB|a

	1. 
		
		Can be produced.  
	
		S
		
			->(rule 1 on first S)
			
		AaBb
		
			->(rule 2 on first A)
			
		baBb
		
			->(rule 2 on first B)
			
		baab
	
	2. 
	
		Cannot be generated with this grammar.
	
	
	3. 
	
		Cannot be generated with this grammar.
	
	
	4.
	
		can be produced
		
		S
		
			->(rule 1 on first S)
			
		AaBb
		
			->(rule 1 on first A)
			
		AbaBB
		
			->(rule 2 on first B)
			
		Abaab
		
			->(rule 2 on first A)
			
		bbaab




##1e)

consider the following grammar

	
	S::= aScB|A|b
	
	A::= cA|c
	
	B::= d|A



	1. abcd
	
		this sentence is producible with the following parse tree
		
							    S
						   /  /   \  \
						  a  S     c  B
						  |   |    |  |
						  |   b    c  d
						  |   |    |  |
						  a   b    c  d
	
	2. acccbd
	
		this sentence is not reproducible with our grammar
		
		
	3. acccbcc
	
		this sentence is not reproducible with our grammar
		
	4. acd
		
		this sentence is not reproducible with our grammar
		
	5. accc
		
		this sentence is reproducible with the following parse tree
		
								 S
							/  /   \  \  
						   a  S     c  B
						   |  |     |  |
						   |  A     |  A
						   |  |     |  |
						   a  c     c  c



##2a)

	Grammar option 1:  e::= operand|e operator operand
	Grammar option 2:  e::= operand esuffix
					   esuffix::= operator operand esuffix|epsilon
					   
	i) option 1 generates either operand or e(recursively) operator operand.  This means
	   we either have operand or operand operator operand...operand, growing to the left 
	   the more we recurse e.  It will always begin with operand and end with operand.
	   
	   option 2 generates operand and esuffix (in this order), esuffix produces operator
	   operand operator... operand epsilon, always beginning with operand and ending with 
	   operand epsilon.
	   
    ii) These two options produce the same grammar since they will always alternate between
       operator and operand, beginning and ending with operand.  
       

##2b)
	The statement 40-3<<4 will determine precedence between the operations - and <<.  If -
	has precedence over <<, this will be equivalent to the statement (40-3)<<4 = 592.  If 
	<< has precedence, it will be equivalent to 40-(3<<4) = 8.  Our output was 542, meaning
	- has precidence over <<.
	
##2c) 
	Flp::= S Di * De Di * Exp | S Di + De Di * Exp
	S::= +|-
	De::= .
	Exp::= S|Di
	Di::= Di N|M
	N::= 0|1|2|3|4|5|6|7|8|9
	M::= 1|2|3|4|5|6|7|8|9
	