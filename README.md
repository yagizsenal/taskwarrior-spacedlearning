# taskwarrior-spacedlearning
This is a [taskwarrior](https://taskwarrior.org/) hook script that automatically manages the next time of the task according to [Spaced Learning](https://www.oxfordlearning.com/what-is-spaced-practice/) method.

# How to install

1. Add these lines to your `.taskrc`

```
uda.spacedLearning.type=string
uda.spacedLearning.label=SpacedLearning
uda.spacedLearning.values=exclude,day0,day1,day3,day7,day14
uda.spacedLearning.default=exclude
```
2. Copy `on-modify.spaced-learning-recur` to your `.task/hooks` directory.

3. Run `task diag`. Under **Hooks** tab, you should see
`Active: on-modify.spaced-learning-recur (executable)`

# How to use

While you add a task you can add the spaced learning state of the task by adding `spacedLearning` attribute. After you comlete the task by `task done`, next review day is calculated and the task is updated.

Current attribute values:
| Value         | Description                                                     |
| ------------- |:---------------------------------------------------------------:|
| `exclude`     | Do not recur this task                                          |
| `day0`        | First iteration of the task, recurs next day                    |
| `day1`        | Second iteration of the task, recurs two days later             |
| `day3`        | Third iteration of the task, recurs four days later             |
| `day7`        | Fourth iteration of the task, recurs seven days later           |
| `day14`       | Fifth iteration of the task, after this the task does not recur.|

