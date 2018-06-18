
I'm doing the _Data Scientist In Python Path_ at https://www.dataquest.io/. I really like the website and the exercises so far are good challenges.

I'm using this occasion to practise using github more, so that's why I'm uploading some stuff. I appreciate that this is a beginner's problem, but I just want to practise not only programming but also using github. (see my post on )


So, this exercise was the following:

The dataset file `nfl.csv` includes headers `year`, `week`, `winner`, `loser` and has lots of rows that tell you when an NFL game was played and who won.

The idea of the exercise is to create a class (Dataset) and add a method which given a value for a column, pulls out all the rows for that column.

So the challenge was not only to write down a correct method for that class, but also to instruct a method to iterate appropriately and give for output a list of values (if the input was a genuine column), or None if the input was not an actual column in the dataset `nfl.csv`.

This is my answer:

```python
# Default display code
class Dataset:
    def __init__(self, data):
        self.header = data[0]
        self.data = data[1:]

    # Add your method here.
    def column(self, label):
        output = []
        if label in self.header:
            for ind_column, value_column in enumerate(self.header):
                if label == value_column:
                    for ind_row, value_row  in enumerate(self.data):
                        output.append(self.data[ind_row][ind_column])
            return(output)
        else:
            return(None)
            player_column = nfl_dataset.column('player')

nfl_dataset = Dataset(nfl_data)
year_column = nfl_dataset.column('year')
```

For me the challenge was first to write down the method properly. I was struggling on when to add the `self.` bit; and then on coding the method itself.

It took me a while to realise I had to use two iterations with `enumerate()`.

Then, I had a correct programme, but the output was not ok and I had the error while instructing the outcome. I had put `print(outcome)` and that wasn't what the exercise required. Anyway, one of those moments where you know you're doing it right and you can't understand why the answer is strictly speaking incorrect.
