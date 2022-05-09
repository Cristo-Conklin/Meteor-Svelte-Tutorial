<script>
    import { TasksCollection } from "../api/TasksCollection";

    export let task;

    const toggleChecked = () =>
            Meteor.call('tasks.setIsChecked', task._id, !task.isChecked);

    const deleteThisTask = () => Meteor.call('tasks.remove', task._id);
    // const toggleChecked = () => {
    //     // Set the isChecked property to the opposite of its current value
    //     TasksCollection.update(task._id, {
    //         $set: { isChecked: !task.isChecked },
    //     });
    // };
    // const deleteThisTask = () => {
    //     TasksCollection.remove(task._id);
    // };
</script>

<li class="task">
    <input
        type="checkbox"
        readonly
        checked={!!task.isChecked}
        on:click={toggleChecked}
    />
    <span class="text">{task.text}</span>
    <button class="delete" on:click={deleteThisTask}>&times;</button>
</li>
