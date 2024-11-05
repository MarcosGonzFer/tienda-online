<script>
  let count = $state(0)
  const sumar = () => {
    count += 1
  }
  const restar = () => {
    count -= 1
  }
</script>

<button onclick={sumar}>
sumar {count}
</button>
<button onclick={restar}>
restar {count}
</button>
