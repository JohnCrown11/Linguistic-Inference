import numpy as np
import random
alphabet = {"a": np.array([[0.76, 0.3],[0.1, 0.76]]), 
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
            "r": np.array([[0.675, 0.3],[0.132, 0.675]]),
            "s": np.array([[7, 12],[2, -1]]),
            "t": np.array([[0.625, 0.2],[0.18, 0.625]]),
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
    

#print(checkDensityValidity(Pl, Pr))
#print(phi(wordMult("rat"), Pl, Pr))
#print(phi(wordMult("tar"), Pl, Pr))
#print(phi(wordMult("art"), Pl, Pr))


def grabValues(iterations, gap, start):
  iter = 0
  for a in range(iterations):
    for b in range(iterations):
      for c in range(iterations):
        for d in range(iterations):
          for e in range(iterations):
            for f in range(iterations):
              for g in range(iterations):
                h=(1-((a*gap+start)*(e*gap+start)+(b*gap+start)*(g*gap+start)+(c*gap+start)*(f*gap+start)))/(d*gap+start)
                m1 = np.array([[a*gap+start, b*gap+start],[c*gap+start, d*gap+start]])
                m2 = np.array([[e*gap+start, f*gap+start],[g*gap+start, h]])
                print(iter)
                print(h)
                print(np.dot(m1, m2))
                #print((a*gap+start)*(e*gap+start)+(b*gap+start)*(g*gap+start)+(c*gap+start)*(f*gap+start)+((d*gap+start)*(h)))
                iter += 1
def grabValuesRandom(iterations, high):
  iter = 0
  for a in range(iterations):
    a1 = (random.random()*100) % high
    for b in range(iterations):
      b1 = (random.random()*100) % high
      for c in range(iterations):
        c1 = (random.random()*100) % high
        for d in range(iterations):
          d1 = (random.random()*100) % high
          for e in range(iterations):
            e1 = (random.random()*100) % high
            for f in range(iterations):
              f1 = (random.random()*100) % high
              for g in range(iterations):
                g1 = (random.random()*100) % high
                h=(1-(a1*e1+b1*g1+c1*f1))/d1
                m1 = np.array([[a1, b1],[c1, d1]])
                m2 = np.array([[e1, f1],[g1, h]])
                print(iter)
                print(h)
                print(np.dot(m1, m2))
                iter += 1
                #print(a1*e1+b1*g1+c1*f1+d1*h)
grabValuesRandom(2, 1)
