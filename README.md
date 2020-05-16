# English-Synonym-Translator
## A Short Python Program using Datamuse API to create an English synonym translator

Translate Function that calls the Datamuse API
def translate(lst):
    tran=[]
    for i in lst:
        baseurl = "https://api.datamuse.com/words"
        params_diction = {} # Set up an empty dictionary for query parameters
        params_diction["ml"] = i
        params_diction["max"] = "1" # get at most 3 results
        resp = requests.get(baseurl, params=params_diction)
        word_ds = resp.json()
        tran.append([d['word'] for d in word_ds])
    return tran
        

inp=input("Enter string to be translated:")
print(inp)
lst=inp.split()
#print(lst)
s=translate(lst)
#print(s)
lst=[' '.join(strings) for strings in s]
res=' '.join(lst)
print(res)
