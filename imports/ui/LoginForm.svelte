<script>
    import { Meteor } from 'meteor/meteor';

    let username = "";
    let password = "";

    const handleSubmit = () => {
        Meteor.loginWithPassword(username, password);
    }
</script>

<form class="login-form" on:submit|preventDefault={handleSubmit}>
    <div>
        <label for="username">Username
            <input
                    type="text"
                    placeholder="Username"
                    name="username"
                    required
                    bind:value={username}
            />
        </label>

    </div>

    <div>
        <label for="password">Password
            <input
                    type="password"
                    placeholder="Password"
                    name="password"
                    required
                    bind:value={password}
            />
        </label>

    </div>

    <div>
        <button type="submit">Log In</button>
    </div>
</form>