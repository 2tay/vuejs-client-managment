<template>
    <ul id="nav">
        <!-- 
      <router-link
        :to="{ name: 'Home', params: { pageTitle: 'Home' } }"
        tag="li"
        exact
        ><a>Home</a></router-link
      > 
        <router-link
        :to="{ name: 'About', params: { pageTitle: 'About' } }"
        tag="li"
        ><a>About</a></router-link
      > 
      -->
        <router-link :to="{ name: 'clients', params: { pageTitle: 'clients' } }" tag="li" exact><a>clients</a></router-link>
        <router-link :to="{ name: 'dashboard', params: { pageTitle: 'dashboard' } }" tag="li"><a>dashboard</a></router-link>

        <a href="#" @click="logout">Logout</a>
    </ul>
</template>
  
<script>
export default {
    name: "Navbar",
    data() {
        return {
            userLoggedInObj: localStorage.getItem("admin-info"),
        };
    },
    methods: {
        logout() {
            localStorage.clear();
            this.$router.push({ name: "login" });
            console.warn("Logging out...");
        },
    },
};
</script>
  
<style scoped lang="scss">
$fontColor: darkcyan;
$navSelectedColor: #325a5a;

ul {
    display: flex;
    justify-content: center;
    list-style: none;
    margin-bottom: 50px;

    a {
        text-decoration: none;
        font-weight: bold;
        color: $fontColor;
        padding: 10px;
    }

    // a:hover {
    //   color: $navSelectedColor;
    //   box-shadow: 2px 2px 4px 0px #325a5a;
    // }
    a {
        // display: inline-flex;
        padding: 10px;
    }
}

a.router-link-exact-active a,
ul a a:hover {
    color: $navSelectedColor;
    /*
    border-bottom: 2px solid $navSelectedColor;
    box-shadow: 0px 3px 2px #bfb3;
    */
    box-shadow: 2px 2px 4px 0px #325a5a;
}
</style>
  