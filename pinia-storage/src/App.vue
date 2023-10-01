<template>
  <header>
    <h1>Pinia サンプル</h1>
  </header>
  <main>
    <RouterView/>
  </main>
</template>

<style>
header{
  position: fixed;
  margin-top: 1rem;
  width: 100%;
  height: 50px;
  top: 0;
  z-index: 999;
}
main{
  border: blue 1px solid;
}

#breadcrumbs ul li {
  display: inline;
  list-style-type: none;
}

#breadcrumbs {
  margin-left: 0px;
}

#breadcrumbs ul{
  padding-left: 0px;
}

#breadcrumbs ul .current{
  color: red
}

#breadcrumbs ul li:before{
  content: " > "
}

#breadcrumbs ul li:first-child:before{
  content: none
}
</style>
