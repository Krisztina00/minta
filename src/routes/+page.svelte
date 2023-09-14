<script>
    let shoppingList = [];
    let newItem = "";
  
    function addItem() {
      if (newItem.trim() !== "") {
        shoppingList = [...shoppingList, newItem.trim()];
        newItem = "";
      }
    }
  
    function removeItem(index) {
      shoppingList.splice(index, 1);
    }
  </script>
  
  <main>
    <h1>Bevásárló Lista</h1>
  
    <form on:submit|preventDefault={addItem}>
      <input bind:value={newItem} placeholder="Új elem hozzáadása" />
      <button type="submit">Hozzáadás</button>
    </form>
  
    <ul>
      {#each shoppingList as item, index (item)}
        <li>
          {item}
          <button on:click={() => removeItem(index)}>Törlés</button>
        </li>
      {/each}
    </ul>
  </main>
  
  <style>
    main {
  text-align: center;
  margin: 20px;
}

h1 {
  font-size: 24px;
  margin-bottom: 20px;
}

form {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

input {
  padding: 8px;
  font-size: 16px;
  margin-right: 10px;
}

button {
  padding: 8px 16px;
  font-size: 16px;
  background-color: #719ece;
  color: #fff;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

li button {
  margin-left: 10px;
  padding: 4px 8px;
  font-size: 14px;
  background-color: #cd85b3;
  color: #fff;
  border: none;
  cursor: pointer;
}

li button:hover {
  background-color: #cd85b3;
}
  </style>
  
