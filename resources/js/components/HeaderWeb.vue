<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
            <div class="container">
                <a class="navbar-brand" href="/">Laravel Boolpress</a>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>

                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav mr-auto w-100 align-items-center">
                        <li class="nav-item active">
                            <router-link class="nav-link" to="/">
                                Home
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link class="nav-link" to="/about">
                                About
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link class="nav-link" to="/contacts">
                                Contacts
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link class="nav-link" to="/tags">
                                Tags
                            </router-link>
                        </li>
                        <li class="nav-item ml-auto">
                            <a href="/admin" class="ms_link badge badge-light">
                                Login
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'HeaderWeb',
}
</script>

<style lang="scss" scoped>
.ms_link{
    font-size: 14px;
}
</style>