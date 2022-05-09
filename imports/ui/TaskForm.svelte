<script>
    import { TasksCollection } from "../api/TasksCollection";

    let newTask = "";

    // export let user = null;

    const handleSubmit = () => {
        // Insert a task into the collection
        // TasksCollection.insert({
        //     text: newTask,
        //     createdAt: new Date(), // current time
        //     userId: user._id,
        // });
        if (!newTask) return;

        Meteor.call("tasks.insert", newTask);

        // Clear form
        newTask = "";
    };
</script>

<form class="task-form" on:submit|preventDefault={handleSubmit}>
    <input
        type="text"
        name="text"
        placeholder="Type to add new tasks"
        bind:value={newTask}
    />
    <button type="submit">Add Task</button>
</form>
