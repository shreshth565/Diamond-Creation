import React from "react"; import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";

function Home() { return ( <div className="min-h-screen bg-pink-100 text-gray-800 p-6"> <header className="text-center mb-10"> <h1 className="text-4xl font-bold text-pink-600">Diamond Creation</h1> <p className="text-lg mt-2">Explore our delightful range of pastel stationery</p> </header> <main className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6"> {["Notebooks", "Pens", "Stickers", "Planners", "Art Supplies", "Envelopes"].map((item) => ( <div key={item} className="bg-white p-4 rounded-2xl shadow-md hover:shadow-lg transition"> <h2 className="text-xl font-semibold text-pink-500">{item}</h2> <p className="text-sm mt-1">High-quality and charming {item.toLowerCase()} for every mood.</p> </div> ))} </main> <footer className="mt-10 text-center"> <Link to="/about" className="text-pink-600 underline">Learn more about us</Link> </footer> </div> ); }

function About() { return ( <div className="min-h-screen bg-purple-100 text-gray-800 p-6"> <header className="text-center mb-10"> <h1 className="text-4xl font-bold text-purple-600">About Diamond Creation</h1> <p className="text-lg mt-2">Where creativity meets quality in pastel perfection.</p> </header> <section className="max-w-3xl mx-auto text-center"> <p className="text-md mb-4"> Diamond Creation is your go-to destination for beautiful, functional, and inspiring stationery. Whether you're a student, an artist, or just someone who loves writing, our pastel-themed products bring a touch of charm and joy to your everyday tasks. </p> <Link to="/" className="text-purple-600 underline">Back to Home</Link> </section> </div> ); }

export default function App() { return ( <Router> <Routes> <Route path="/" element={<Home />} /> <Route path="/about" element={<About />} /> </Routes> </Router> ); }
 </section>
 <footer>
 <p>&copy;2025Diamond Creation.All right reserved.</p>
 </footer>
 </body>
 </html>
