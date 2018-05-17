class WordCounter:

    def __init__(self, file):
        self.file = file
        self.words = {}

    def read(self):
        f = open(self.file, 'r')
        full_text = f.read()
        full_new = [line.strip() for line in full_text.split()]
        for word in full_new:
            if word in self.words and word.isalpha():
                self.words[word] += 1
            else:
                self.words[word] = 1
        w = sorted(self.words.items(), key=lambda x: x[-1])[::-1]
        print(w)


f1 = WordCounter("file1.txt")
f1.read()
