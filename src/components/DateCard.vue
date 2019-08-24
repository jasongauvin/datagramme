<template>
  <div class="history">
    <h2>A MOMENT OF HISTORY</h2>
    <p>You entered {{dates.length}} dates...</p>
  </div>
    <li class="date">
      <h2>{{date.date}}</h2>
      <p>{{date.text}}</p>
    </li>
</template>

<script>
export default {
  name: "DateCard",
</script>

<style lang="scss" scoped>
.history{
  margin-top: 50px;
  margin-bottom: 20px;
  background: black;
  padding: 20px;
  text-align: center;
  border-radius: 10px;
  color: white;
  h2{
    margin-bottom: 5px;
  }
  p{
    font-weight: bold;
  }
}

.date{
  padding: 20px;
  background: white;
  border-radius: 10px;
  color: black;

  &:not(:last-child){
    margin-bottom: 20px;
  }

  h2{
    font-weight: bold;
    margin-bottom: 20px;
  }
}
</style>