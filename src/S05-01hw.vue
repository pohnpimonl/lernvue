<template>
    <div class="container">
        <nav class="navbar">
            <div class="logo">
                <img src="./assets/logo.png" />
            </div>
            <ul class="menu">
                <li>Home</li>
                <li>List</li>
            </ul>
        </nav>
        <main class="main">
            <section class="section section1">
                Section 1
            </section>
            <section class="section section2">
                Section 2
            </section>
        </main>
    </div>
</template>

<script>
export default {

}
</script>

<style>
html, body {
    margin: 0;
    padding: 0;
    font-family: sans-serif;
}
*, *::before, *::after {
    box-sizing: border-box;
}
.navbar {
    box-shadow: 0 10px 10px #EEE;
    display: flex;
    padding: 0 24px;
    align-items: center;
    background-color: #CDF2CA;
}
.logo {
    flex: 1;
}
.logo img {
    height: 36px;
}
.menu {
    list-style: none;
    display: flex;
    flex-direction: row;
    font-weight: bold;
}
.menu li {
    padding: 16px;
    color: #798777;
}
.main {
    padding: 24px;
    display: flex;
    flex-direction: row;
}
.section {
    background-color: #FFF;
    box-shadow: 0 2px 10px #E0E0E0;
    padding: 24px;
    border-radius: 8px;
    height: 240px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    color: #AAA;
}
.section1 {
    flex: 5;
    margin-right: 24px;
}
.section2 {
    flex: 3;
}
</style>