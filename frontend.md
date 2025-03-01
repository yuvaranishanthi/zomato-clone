# zomato-clone
import React from "react";
import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";

const Home = () => <div className="p-6 text-xl">Welcome to Zomato Clone</div>;

const Restaurants = () => {
  const restaurants = [
    { name: "Pizza Hut", image: "https://source.unsplash.com/300x200/?pizza" },
    { name: "McDonald's", image: "https://source.unsplash.com/300x200/?burger" },
    { name: "Starbucks", image: "https://source.unsplash.com/300x200/?coffee" },
  ];

  return (
    <div className="p-6">
      <h2 className="text-2xl font-bold mb-4">List of Restaurants</h2>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
        {restaurants.map((restaurant, index) => (
          <div key={index} className="border rounded-lg shadow-lg p-4">
            <img src={restaurant.image} alt={restaurant.name} className="w-full h-40 object-cover rounded-lg" />
            <h3 className="text-lg font-semibold mt-2">{restaurant.name}</h3>
          </div>
        ))}
      </div>
    </div>
  );
};

const Orders = () => <div className="p-6 text-xl">Your Orders</div>;

const Navbar = () => (
  <nav className="bg-red-500 p-4 text-white flex justify-between">
    <h1 className="text-2xl font-bold">Zomato Clone</h1>
    <div>
      <Link className="px-4" to="/">Home</Link>
      <Link className="px-4" to="/restaurants">Restaurants</Link>
      <Link className="px-4" to="/orders">Orders</Link>
    </div>
  </nav>
);

const App = () => {
  return (
    <Router>
      <Navbar />
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/restaurants" element={<Restaurants />} />
        <Route path="/orders" element={<Orders />} />
      </Routes>
    </Router>
  );
};

export default App;
