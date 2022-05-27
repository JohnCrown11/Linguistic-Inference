# Linguistic-Inference
Linear Algebra Module 8, end of year project.
import numpy as np

alphabet = {"a": np.array([[0.76, 0.15],[0.1, 0.76]]), 
            "b": np.array([[7, 12],[2, -1]]), 
            "c": np.array([[7, 12],[2, -1]]), 
            "d": np.array([[7, 12],[2, -1]]), 
            "e": np.array([[7, 12],[2, -1]]), 
            "f": np.array([[7, 12],[2, -1]]), 
            "g": np.array([[7, 12],[2, -1]]),
            "h": np.array([[2, 6],[8, 11]]),
            "i": np.array([[1, 2],[3, 4]]),
            "j": np.array([[7, 12],[2, -1]]),
            "k": np.array([[7, 12],[2, -1]]),
            "l": np.array([[7, 12],[2, -1]]),
            "m": np.array([[7, 12],[2, -1]]),
            "n": np.array([[7, 12],[2, -1]]),
            "o": np.array([[7, 12],[2, -1]]),
            "p": np.array([[7, 12],[2, -1]]),
            "q": np.array([[7, 12],[2, -1]]),
            "r": np.array([[0.675, 0.11],[0.132, 0.675]]),
            "s": np.array([[7, 12],[2, -1]]),
            "t": np.array([[0.625, 0.19],[0.18, 0.625]]),
            "u": np.array([[7, 12],[2, -1]]),
            "v": np.array([[7, 12],[2, -1]]),
            "w": np.array([[7, 12],[2, -1]]),
            "x": np.array([[7, 12],[2, -1]]),
            "y": np.array([[7, 12],[2, -1]]),
            "z": np.array([[7, 12],[2, -1]]),
           }

Pl = np.array([[3/4, 0], [0, 1/2]])
Pr = np.array([[2/3, 0], [0, 1]])

def wordMult(word):
  if(len(word) == 1): return alphabet.get(word)
  mp = np.dot(alphabet.get(word[len(word)-2]), alphabet.get(word[len(word)-1]))
  if(len(word) == 2): 
    return mp
  for i in range(len(word)-2):
    mp = np.dot(alphabet.get(word[len(word)-i-3]), mp)
  return mp
def getTrace(arr):
  return np.trace(arr)

def checkDensityValidity(Pl, Pr):
  mp = np.dot(Pl, Pr)
  return (getTrace(mp) == 1)

def phi(M, Pl, Pr):
  M_cross = np.asmatrix(M).getH() # gets complex conjugate transpose
  mp = np.dot(Pr, M_cross)
  mp = np.dot(M, mp)
  mp = np.dot(Pl, M)
  return getTrace(mp)
    

print(checkDensityValidity(Pl, Pr))
print(phi(wordMult("rat"), Pl, Pr))
print(phi(wordMult("tar"), Pl, Pr))
print(phi(wordMult("art"), Pl, Pr))
