# The discussion so far: #

TJH:

What do you suggest for extended CA neighborhood rule tables?

Calcyman:

I'm not sure that it's possible to get this to represent a triangular neighborhood, but it can do hexagonal, 1D and 3D:

```
-----------------------------------------------------------------------

#Define number of dimensions

dimensions:{x,y}

#Define neighborhood

neighbor c={x,y}
neighbor n={x,y-1}
neighbor ne={x+1,y-1}
neighbor e={x+1,y}
neighbor se={x+1,y+1}
neighbor s={x,y+1}
neighbor sw={x-1,y+1}
neighbor w={x-1,y}
neighbor nw={x-1,y-1}

#Define symmetries
#This contains all equivalent permutations of c,n,ne,e,se,s,sw,w,nw:
#In this case, it represents rotate4 symmetry

symmetry:c,n,ne,e,se,s,sw,w,nw
symmetry:c,e,se,s,sw,w,nw,n,ne
symmetry:c,s,sw,w,nw,n,ne,e,se
symmetry:c,w,nw,n,ne,e,se,s,sw


#Define display matrix

matrix:1.0,0.0
matrix:0.0,1.0

#This is the identity matrix, which means that the world
#coordinates translate directly into screen coordinates.
#
#For hexagonal coordinates, use a matrix of:
#
# 1.0,0.5
# 0.0,0.8660254
#
#The display matrix has two rows, and the same number of
#columns as dimensions. It represents the transformation
#from world coordinates to display coordinates.

#Now add the rest of the rule table information.

```

TJH:

This is an interesting idea. Golly would only be able to accept a very limited subset of these, of course.

What about block CA? (partitioning ones, like the Margolus neighborhood?). Any ideas there? As with the triangular neighborhood the complication is that the neighborhood isn't fixed across all cells in all timesteps.

Calcyman:

It can be accomplished by using a temporal variable, t, that represents the time in generations. Then, the Margolus neighborhood would become:

```

#centre neighbor
neighbor c={x,y}

#horizontal neighbor
neighbor h={x+2*((x+t) % 2)-1,y}

#vertical neighbor
neighbor v={x,y+2*((y+t) % 2)-1}

#diagonal neighbor
neighbor d={x+2*((x+t) % 2)-1,y+2*((y+t) % 2)-1}

```

The percent symbol here is used to represent the modulus operator.
Now you can see how flexible the system is. By the way, a 2-state
triangular rule could be expressed as a 64-state hexagonal rule.