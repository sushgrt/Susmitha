# Susmitha

##I have compressed both the functions into a one single function.The makeCacheMatrix returns the list of get,set and Cache solve functions.The Cache Solve function checked if there is any cached data avaiable else it calculates the inverse of the matrix.

makeCacheMatrix <- function(x = matrix()) {
m <- NULL
set <- function(y) {
x <<- y
m <<- NULL
}
get <- function() x
cacheSolve <- function (...) {
if(!is.null(m)) {                          
message("getting cached data")
} else {
m<<-solve(x,...)
}
return(m)
}
list(set = set, get = get,
cacheSolve = cacheSolve)                                                   
}
