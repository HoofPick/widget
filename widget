document.addEventListener("DOMContentLoaded", () => {
  const API_URL = "https://hoofpick.com/api/v3/listing/categories.json";
  const API_KEY = "d303-273f-91c4-7f08-ac57-1367-49c4-a2df";

  fetch(API_URL, {
    headers: {
      "X-API-KEY": API_KEY,
      "Accept": "application/json"
    }
  })
    .then(response => response.json())
    .then(data => {
      const listingsContainer = document.getElementById("business-listings");
      listingsContainer.innerHTML = "";

      if (data && data.length > 0) {
        data.forEach(listing => {
          const listingElement = document.createElement("div");
          listingElement.className = "listing";

          listingElement.innerHTML = `
            <h3>${listing.name}</h3>
            <p>${listing.description || "No description available."}</p>
            <a href="${listing.url}" target="_blank">View Listing</a>
          `;

          listingsContainer.appendChild(listingElement);
        });
      } else {
        listingsContainer.innerHTML = "<p>No listings found.</p>";
      }
    })
    .catch(error => {
      console.error("Error fetching listings:", error);
      document.getElementById("business-listings").innerHTML = "<p>Error loading listings.</p>";
    });
});
