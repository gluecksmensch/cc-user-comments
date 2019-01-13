<template>
  <section class="user">
    <div id="user">
      <h1>User</h1>
      <UserData v-bind="userData" />
    </div>
    <section id="comments">
      <h2>Comments</h2>
      <ul>
        <li v-for="comment in userComments" :key="comment.id">
          <Comment v-bind="comment" />
        </li>
      </ul>
    </section>
  </section>
</template>

<script>
import Comment from "./Comment";
import UserData from "./UserData";
import axios from "axios";

export default {
  name: "UserComments",
  components: {
    Comment,
    UserData
  },
  data() {
    return {
      userData: null
    };
  },
  computed: {
    userComments() {
      return this.userData && this.userData.comments
        ? this.userData.comments
        : [];
    }
  },
  methods: {
    async fetchUserData() {
      const userPromise = await axios(
        "https://jsonplaceholder.typicode.com/users/1"
      );
      const commentsPromise = await axios(
        "https://jsonplaceholder.typicode.com/posts?userId=1"
      );

      const [{ data: user }, { data: comments }] = await Promise.all([
        userPromise,
        commentsPromise
      ]);
      // console.log(user, comments);

      this.setUserData(user, comments);
    },

    setUserData(user, comments) {
      const userComments = comments.map(comment => {
        return { id: comment.id, title: comment.title, body: comment.body };
      });
      this.userData = Object.assign(user, { comments: userComments });
    }
  },
  mounted() {
    this.fetchUserData();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
