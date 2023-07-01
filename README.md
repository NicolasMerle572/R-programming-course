# R-programming-course
R programming course

     makeCacheMatrix <- function(x = matrix()) {
     # Initialize the inverse matrix cache
      inverse <- NULL
      
      # Function to set the matrix and invalidate the cached inverse
      setMatrix <- function(newMatrix) {
            matrix <<- newMatrix
            inverse <<- NULL
      }
      
      # Function to get the matrix
      getMatrix <- function() {
            matrix
      }
      
      # Function to compute the inverse of the matrix using caching
      cacheSolve <- function() {
            if (!is.null(inverse)) {
                  # If the inverse is already cached, retrieve it
                  message("Retrieving cached inverse...")
                  inverse
            } else {
                  # If the inverse is not cached, compute it and cache it
                  message("Computing inverse and caching...")
                  inverse <- solve(matrix)
                  inverse
            }
      }
      
      # Create and return a list of the functions
      list(setMatrix = setMatrix,
           getMatrix = getMatrix,
           cacheSolve = cacheSolve)
}

     cacheSolve <- function(c(1, 2, 3, 4), nrow = 2) {
        ## Return a matrix that is the inverse of 'x'
        inverse <- solve(x)
        inverse
}

# Example usage
     matrix <- matrix(c(1, 2, 3, 4), nrow = 2)
     inverse <- cacheSolve(matrix)
     print(inverse)
