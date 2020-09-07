<template>
  <Layout>
    <g-image alt="Example image" src="~/favicon.png" width="135" />
    <article>
      <h1>Articles ({{ $page.allContentfulBlog.totalCount }})</h1>
      <section v-for="edge in $page.allContentfulBlog.edges" :key="edge.node.fields">
        {{ edge }}
        <h2>{{ edge.node.title }}</h2>
        <p>{{ edge.node.article }}</p>
      </section>
    </article>
  </Layout>
</template>

<page-query>
query Index {
  allContentfulBlog {
    totalCount
    edges {
      node {
          title
          article
        }
      }
    }
}
</page-query>

<script>
export default {
  data:function(){
    return{
      title:"title"
    }
  }
}
</script>