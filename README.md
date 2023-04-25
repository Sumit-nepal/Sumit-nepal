const username = Sumit-nepal;
const apiUrl = `https://api.github.com/users/${username}/contributions`;

fetch(apiUrl)
  .then(response => response.json())
  .then(data => {
    let streak = 0;
    for (let i = 0; i < data.length; i++) {
      if (data[i].count > 0) {
        streak++;
      } else {
        break;
      }
    }
    console.log(`Current GitHub streak for ${username}: ${streak} days`);
  })
  .catch(error => console.error(error));
