<template>
  <div class="app">
    <form @submit.prevent>
			<h4>Создание поста</h4>
      <input class="input" 
			type="text"
			 placeholder="Название" 
			v-model="title"
			@input="title = $event.target.value"/>

      <input class="input" 
			type="text" 
			placeholder="Описание" 
			v-model="body"/>

			<button class="btn" @click="createPost">Создать</button>
    </form>
    <div class="post" v-for="post in posts" :key="post.id">
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
			title: '',
			body: '',
      posts: [
        {
          id: 1,
          title: "Пост о JavaScript",
          body: "JavaScript универсальный язык программирования",
        },
        {
          id: 2,
          title: "Пост о JavaScript 2",
          body: "JavaScript универсальный язык программирования 1",
        },
        {
          id: 3,
          title: "Пост о JavaScript 3",
          body: "JavaScript универсальный язык программирования 2",
        },
        {
          id: 4,
          title: "Пост о JavaScript 4",
          body: "JavaScript универсальный язык программирования 3",
        },
      ],
    };
  },
  methods: {
		createPost() {
			const newPost = {
				id: Date.now(),
				title: this.title,
				body: this.body
			}

			this.posts.push(newPost);

			this.title = '';
			this.body = '';

		},
	},
};
</script>

<style >
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
	padding: 20px;
}

.post {
  padding: 15px;
  margin-top: 15px;
  border: 1px solid teal;
}

form {
	display: flex;
	flex-direction: column;
}

.btn {
	align-self: flex-end;
	margin-top: 10px;
	padding: 10px 15px;
	background: none;
	color: teal;
	border: 1px solid teal;
}

.input {
	width: 100%;
	border: 1px solid teal;
	padding: 5px;
	margin-top: 10px;
}
</style>



