Model Selection
------

Most models contain _hyper-parameters_: parameters that are specified in the
constructor, and not derived from the data. ScikitLearn.jl provides
`GridSearchCV` to find the best set of hyper-parameter:

```julia
using ScikitLearn.GridSearch: GridSearchCV

gridsearch = GridSearchCV(LogisticRegression(), Dict(:C => 0.1:0.1:2.0))
fit!(gridsearch, X, y)
println("Best hyper-parameters: $(gridsearch.best_params_)")
```

See `?GridSearchCV` and the [scikit-learn docs](http://scikit-learn.org/stable/modules/grid_search.html) for details.

### Examples

- [Quick start guide](quickstart.md)
- [Pipelining: chaining a PCA and a logistic regression](https://github.com/cstjean/ScikitLearn.jl/blob/master/examples/Pipeline_PCA_Logistic.ipynb)
- [Concatenating multiple feature extraction methods](https://github.com/cstjean/ScikitLearn.jl/blob/master/examples/Feature_Stacker.ipynb)