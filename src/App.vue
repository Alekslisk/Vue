<template>
  <div id="app">
    <header>
      <nav>
        <div class="logo">My blog</div>
        <ul class="nav-links">
          <li><a href="#">Home</a></li>
          <li><a href="#">Politics</a></li>
          <li><a href="#">Tech</a></li>
          <li><a href="#">Entertainment</a></li>
          <li><a href="#">Travel</a></li>
          <li><a href="#">Sports</a></li>
        </ul>
      </nav>
    </header>

    <section class="blog-section">
      <div class="blog-container">
        <div class="blog-card" v-for="(post, index) in posts" :key="index">
          <img :src="post.image" alt="Blog Image">
          <div class="content">
            <h3>{{ post.title }}</h3>
            <p>{{ post.date }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      posts: [
        {
          title: "Sageburner company",
          date: "July 19, 2019",
          image: require('@/assets/one.jpg')
        },
        {
          title: "Magnificant one",
          date: "July 19, 2019",
          image: require('@/assets/two.png')
        },
        {
          title: "The 20 Biggest Fintech Companies In America 2019",
          date: "July 19, 2019",
          image: "https://avatars.mds.yandex.net/i?id=2e9050b4ebcd52ec892943a7ebe0e76f111306bf-5031604-images-thumbs&n=13"
        }
      ]
    };
  }
};
</script>

<style scoped>
#app {
  font-family: Arial, sans-serif;
}

header {
  background-color: #fff;
  padding: 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 24px;
  font-weight: bold;
}

.nav-links {
  list-style: none;
  display: flex;
}

.nav-links li {
  margin-left: 20px;
}

.nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
}


.blog-section {
  padding: 50px;
  background-color: #f9f9f9;
}

.blog-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.blog-card {
  background-color: #fff;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.blog-card img {
  width: 100%;
  height: auto;
}

.blog-card .content {
  padding: 20px;
}

.blog-card h3 {
  font-size: 18px;
  margin-bottom: 10px;
}

.blog-card p {
  font-size: 14px;
  color: #777;
}

.blog-card:hover {
  transform: translateY(-5px);
}
</style>
