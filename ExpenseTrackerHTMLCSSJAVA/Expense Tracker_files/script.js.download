let expenses = JSON.parse(localStorage.getItem("expenses")) || [];

// Add Expense
function addExpense() {
  let amount = document.getElementById("amount").value;
  let category = document.getElementById("category").value;
  let desc = document.getElementById("desc").value;
  let date = document.getElementById("date").value;

  if (!amount || !category || !desc || !date) {
    alert("⚠ Please fill all fields!");
    return;
  }

  let expense = {
    amount: parseFloat(amount),
    category,
    desc,
    date
  };

  expenses.push(expense);
  localStorage.setItem("expenses", JSON.stringify(expenses));

  document.getElementById("amount").value = "";
  document.getElementById("category").value = "";
  document.getElementById("desc").value = "";
  document.getElementById("date").value = "";

  displayExpenses();
}

// Display Expenses
function displayExpenses() {
  let table = document.getElementById("expenseTable");
  table.innerHTML = "";
  let total = 0;

  expenses.forEach((exp, index) => {
    let row = `<tr>
      <td>${exp.date}</td>
      <td>${exp.category}</td>
      <td>${exp.desc}</td>
      <td>₹${exp.amount}</td>
      <td><button class="delete-btn" onclick="deleteExpense(${index})">Delete</button></td>
    </tr>`;
    table.innerHTML += row;
    total += exp.amount;
  });

  document.getElementById("total").textContent = total;
}

// Delete Expense
function deleteExpense(index) {
  expenses.splice(index, 1);
  localStorage.setItem("expenses", JSON.stringify(expenses));
  displayExpenses();
}

// Initial Load
displayExpenses();
