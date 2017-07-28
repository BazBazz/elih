
# ELIH: Explain Machine Learning predictions like I'm a human

A library to translate Machine Learning classifiers predictions in a human understandable and simplified form.
Based on the ELI5 library, on top of which ELIH adds explanations transformation and formatting layers to make it easy to customize for each project or language.

Still in early stage! But feel free to test & discuss.

## Usage example

```python

# Should be tested in the context of the XGBoost + Titanic ELI5 example
# https://github.com/TeamHG-Memex/eli5/blob/master/docs/source/_notebooks/xgboost-titanic.rst
# chapter 4: "Explaning predictions"

from eli5 import explain_prediction
import elih

explain_prediction(clf, valid_xs[1], vec=vec)
```

![An explanation with raw features](https://github.com/fvinas/elih/blob/master/doc/example1.png)

```python
elih.group(
    explain_prediction(clf, valid_xs[1], vec=vec),
    {
        'Pclass': ['Pclass=1', 'Pclass=2', 'Pclass=3']
    }
)
```

![An explanation with Pclass features regrouped in one place](https://github.com/fvinas/elih/blob/master/doc/example2.png)

## TODO

- implement several layers of rules (computed turn by turn)
- implement a basic (but custom) scoring system (with by default a sigmoid)
- improve export to standard Python dict & list
- implement a Matplotlib radar chart
- implement another layer called "interpretors"
- implement a final layer called "agregators" that regroups variables (from any layer + additional ones) and interprations to display
- add a additional rendering layer? automatic sentences?
- provide a config-file like way to write business rules


