<script>
    import {supabase} from "$lib/supabaseClient"
    let loading = false
    let email;

    const handleLogin = async () => {
        try {
            loading = true
            const { error } = await supabase.auth.signIn({ email })
            if (error) throw error
            alert('Check your email for the login link!')
        } catch (error) {
            alert(error.error_description || error.message)
        } finally {
            loading = false
        }
    }
</script>

<div class="flex items-center justify-center min-h-screen">
    <div class="px-8 py-6 mt-4 text-left bg-white shadow-lg">
        <h3 class="text-2xl font-bold text-center">
            <a href="/">
                <div class="avatar">
                    <div class="w-24 rounded-full">
                        <img width="15" height="15" alt="logo" src="logo.png" />
                    </div>
                </div>
            </a>
        </h3>
        <form on:submit|preventDefault={handleLogin}>
            <div class="mt-4">
                <div>
                    <label class="block" for="email">Email<label>
                        <input
                                bind:value={email}
                                type="email"
                                placeholder="Email"
                               class="w-full px-4 py-2 mt-2 border rounded-md focus:outline-none focus:ring-1 focus:ring-blue-600">
                </div>
                <div class="flex items-baseline justify-center">
                    <input type="submit" class="px-10 py-4 mt-4 text-white bg-blue-600 rounded-lg hover:bg-blue-900"  value={loading ? "Loading" : "Send magic link"} disabled={loading}>
                </div>
            </div>
        </form>
    </div>
</div>
