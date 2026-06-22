<script>
async function loadTiku() {
  const res = await fetch("https://cdn.jsdelivr.net/gh/Wrenpt/README/main/tiku-config.json");
  const tikuList = await res.json();
  console.log("加载成功的题库源：", tikuList);
}
loadTiku();

async function searchQuestion(title, tikuItem) {
  const params = new URLSearchParams({ ...tikuItem.data, q: title });
  const apiRes = await fetch(`${tikuItem.url}?${params}`);
  const data = await apiRes.json();
  const [q, ans] = tikuItem.handler(data);
  return { question: q, answer: ans };
}
</script>
