<script>
  export let item
</script>

<li class="pokemon-stat">
  <span class="stat-name">
    <b>{item.stat.name}: </b>
  </span>
  <span>{item.base_stat}</span>
</li>

<style>
  .stat-name{
    text-transform: capitalize;
  }
</style>

