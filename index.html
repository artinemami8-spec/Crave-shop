import React, { useState, useEffect } from 'react';
import { BrowserRouter as Router, Routes, Route, Link, useParams } from 'react-router-dom';
import { Search, ShoppingBag, User, Trash2, ChevronRight, Star } from 'lucide-react';
import { motion, AnimatePresence } from 'framer-motion';
import { ClerkProvider, SignedIn, SignedOut, SignInButton, UserButton } from "@clerk/clerk-react";

const CLERK_PUBLISHABLE_KEY = "pk_test_cHJlbWl1bS1iZWV0bGUtMzguY2xlcmsuYWNjb3VudHMuZGV2JA";

// --- EXPANDABLE DATA ENGINE ---
// Add your 50 items per category here
const products = [
  { id: 1, name: "VINTAGE OVERSIZED TEE", category: "tshirt", gender: "men", price: 45, image: "https://images.unsplash.com/photo-1583743814966-8936f5b7be1a?q=80&w=500", desc: "Heavyweight 300GSM cotton. Street-ready fit.", sizes: ["S", "M", "L", "XL", "2XL"] },
  { id: 2, name: "BAGGY CARGO PANTS", category: "pants", gender: "unisex", price: 85, image: "https://images.unsplash.com/photo-1552902865-b72c031ac5ea?q=80&w=500", desc: "Multi-pocket tactical design. Water resistant.", sizes: ["30", "32", "34", "36"] },
  { id: 3, name: "CYBERPUNK HOODIE", category: "hoodie", gender: "men", price: 120, image: "https://images.unsplash.com/photo-1556821840-3a63f95609a7?q=80&w=500", desc: "Reflective prints. Ultra-soft fleece interior.", sizes: ["M", "L", "XL"] },
  { id: 4, name: "STREET BEANIE", category: "hats", gender: "unisex", price: 25, image: "https://images.unsplash.com/photo-1576822410457-3a18a9947702?q=80&w=500", desc: "Hand-knitted premium wool.", sizes: ["OS"] },
  { id: 5, name: "DARK SHADES X1", category: "glasses", gender: "women", price: 150, image: "https://images.unsplash.com/photo-1511499767390-a73359586af8?q=80&w=500", desc: "UV400 Protection. Matte black finish.", sizes: ["OS"] },
];

export default function App() {
  const [cart, setCart] = useState([]);
  const [search, setSearch] = useState("");

  return (
    <ClerkProvider publishableKey={CLERK_PUBLISHABLE_KEY}>
      <Router>
        <div className="min-h-screen bg-[#0a0a0a] text-white font-sans selection:bg-red-600">
          
          {/* TOP NAVIGATION */}
          <nav className="fixed top-0 w-full z-50 bg-black/80 backdrop-blur-md border-b border-white/10 px-6 py-4 flex justify-between items-center">
            <Link to="/" className="text-3xl font-black tracking-tighter text-red-600">DRIP.STORE</Link>
            
            <div className="hidden md:flex gap-8 font-bold text-sm tracking-widest uppercase">
              <Link to="/" className="hover:text-red-500 transition">Home</Link>
              <Link to="/buy/men" className="hover:text-red-500 transition">Men</Link>
              <Link to="/buy/women" className="hover:text-red-500 transition">Women</Link>
              <Link to="/buy/all" className="hover:text-red-500 transition font-black text-red-500 underline underline-offset-4">BUY NOW</Link>
            </div>

            <div className="flex items-center gap-5">
              <div className="relative">
                <input 
                  onChange={(e) => setSearch(e.target.value)}
                  className="bg-white/5 border border-white/10 rounded-full px-4 py-1 text-sm focus:w-64 transition-all outline-none" 
                  placeholder="Search gear..."
                />
                <Search className="absolute right-3 top-1.5 text-white/40" size={16}/>
              </div>
              
              <SignedOut><SignInButton mode="modal" className="text-sm font-bold uppercase border border-white px-4 py-1 hover:bg-white hover:text-black transition"/></SignedOut>
              <SignedIn><UserButton /></SignedIn>
              
              <Link to="/cart" className="relative group">
                <ShoppingBag className="group-hover:text-red-500 transition" size={24}/>
                {cart.length > 0 && <span className="absolute -top-2 -right-2 bg-red-600 text-[10px] w-5 h-5 rounded-full flex items-center justify-center font-bold">{cart.length}</span>}
              </Link>
            </div>
          </nav>

          <div className="pt-20">
            <Routes>
              <Route path="/" element={<Home />} />
              <Route path="/buy/:cat" element={<BuyPage search={search} />} />
              <Route path="/product/:id" element={<ProductView products={products} setCart={setCart} />} />
              <Route path="/cart" element={<CartPage cart={cart} setCart={setCart} />} />
            </Routes>
          </div>

        </div>
      </Router>
    </ClerkProvider>
  );
}

// --- HOME PAGE (Welcome Box) ---
function Home() {
  return (
    <div className="h-[90vh] flex flex-col items-center justify-center relative overflow-hidden">
      <motion.div 
        initial={{ opacity: 0, scale: 0.8 }} 
        animate={{ opacity: 1, scale: 1 }}
        className="z-10 text-center space-y-6"
      >
        <h1 className="text-8xl md:text-[12rem] font-black italic leading-none tracking-tighter">NEW DROPS</h1>
        <div className="bg-red-600 p-8 rounded-2xl shadow-2xl shadow-red-500/20 max-w-lg mx-auto">
          <h2 className="text-3xl font-bold">WELCOME TO THE CREW</h2>
          <p className="mt-2 opacity-90 uppercase tracking-widest text-sm">Premium Streetwear & Urban Gear</p>
          <div className="flex gap-4 mt-6 justify-center">
             <Link to="/buy/all" className="bg-black text-white px-8 py-3 font-bold hover:scale-105 transition">START BUYING</Link>
          </div>
        </div>
      </motion.div>
      <div className="absolute top-0 left-0 w-full h-full bg-[url('https://www.transparenttextures.com/patterns/carbon-fibre.png')] opacity-20 pointer-events-none"></div>
    </div>
  );
}

// --- BUY PAGE (Logic for searching clothes/pants/etc) ---
function BuyPage({ search }) {
  const { cat } = useParams();
  const [filter, setFilter] = useState(cat || "all");

  const filteredItems = products.filter(p => {
    const matchesSearch = p.name.toLowerCase().includes(search.toLowerCase()) || p.category.toLowerCase().includes(search.toLowerCase());
    const matchesFilter = filter === "all" || p.gender === filter || p.category === filter;
    return matchesSearch && matchesFilter;
  });

  return (
    <div className="p-8">
      <div className="flex gap-4 mb-10 overflow-x-auto whitespace-nowrap py-2 no-scrollbar">
        {["all", "tshirt", "pants", "hoodie", "hats", "glasses", "men", "women"].map(f => (
          <button key={f} onClick={() => setFilter(f)} className={`px-6 py-2 rounded-full text-xs font-black uppercase tracking-tighter border transition ${filter === f ? 'bg-red-600 border-red-600' : 'border-white/20 hover:border-white'}`}>
            {f}
          </button>
        ))}
      </div>

      <div className="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-6">
        {filteredItems.map(p => (
          <motion.div layout initial={{ opacity: 0 }} animate={{ opacity: 1 }} key={p.id} className="group relative">
            <Link to={`/product/${p.id}`}>
              <div className="aspect-[3/4] overflow-hidden rounded-xl bg-neutral-900">
                <img src={p.image} className="w-full h-full object-cover group-hover:scale-110 transition duration-500" alt={p.name}/>
              </div>
              <div className="mt-4 flex justify-between items-start">
                <div>
                  <h3 className="font-bold text-sm tracking-tight">{p.name}</h3>
                  <p className="text-xs text-white/50 uppercase">{p.category}</p>
                </div>
                <span className="font-black text-red-500">${p.price}</span>
              </div>
            </Link>
          </motion.div>
        ))}
      </div>
    </div>
  );
}

// --- PRODUCT DETAIL PAGE ---
function ProductView({ products, setCart }) {
  const { id } = useParams();
  const [selectedSize, setSelectedSize] = useState("L");
  const product = products.find(p => p.id === parseInt(id)) || products[0];

  return (
    <div className="max-w-7xl mx-auto p-6 md:p-20 grid md:grid-cols-2 gap-16">
      <motion.img initial={{x: -50}} animate={{x: 0}} src={product.image} className="w-full rounded-2xl shadow-2xl border border-white/10" />
      
      <div className="space-y-8">
        <div className="space-y-2">
          <h2 className="text-5xl font-black tracking-tighter uppercase">{product.name}</h2>
          <div className="flex text-yellow-400"><Star size={16}/><Star size={16}/><Star size={16}/><Star size={16}/><Star size={16}/></div>
          <p className="text-3xl font-bold text-red-600">${product.price}</p>
        </div>

        <p className="text-lg text-white/70 leading-relaxed italic border-l-4 border-red-600 pl-4">{product.desc}</p>

        <div>
          <h4 className="text-xs font-black uppercase mb-4 tracking-[0.2em]">Select Size</h4>
          <div className="flex gap-3">
            {product.sizes.map(s => (
              <button 
                key={s} 
                onClick={() => setSelectedSize(s)}
                className={`w-14 h-14 border-2 font-bold transition flex items-center justify-center ${selectedSize === s ? 'bg-white text-black border-white' : 'border-white/20 hover:border-white'}`}
              >
                {s}
              </button>
            ))}
          </div>
        </div>

        <button 
          onClick={() => setCart(prev => [...prev, {...product, selectedSize, cartId: Math.random()}])}
          className="w-full bg-red-600 py-5 font-black text-xl hover:bg-red-700 transition active:scale-95 shadow-xl shadow-red-600/30 uppercase italic"
        >
          Add to Cart
        </button>

        <div className="pt-10 border-t border-white/10">
          <h4 className="font-bold mb-4">RECOMMENDED FOR YOU</h4>
          <div className="grid grid-cols-3 gap-4">
            {products.slice(0,3).map(rp => <Link key={rp.id} to={`/product/${rp.id}`}><img src={rp.image} className="rounded-lg opacity-50 hover:opacity-100 transition"/></Link>)}
          </div>
        </div>
      </div>
    </div>
  );
}

// --- CART PAGE (With Delete Function) ---
function CartPage({ cart, setCart }) {
  const total = cart.reduce((sum, item) => sum + item.price, 0);

  return (
    <div className="max-w-3xl mx-auto p-10">
      <h2 className="text-4xl font-black mb-10 italic uppercase border-b-2 border-red-600 inline-block">Your Stash</h2>
      
      {cart.length === 0 ? (
        <div className="text-center py-20 bg-white/5 rounded-3xl border border-dashed border-white/20">
          <p className="text-xl font-bold opacity-50">STASH IS EMPTY</p>
          <Link to="/buy/all" className="text-red-500 font-bold mt-4 block underline">GO GET SOME GEAR</Link>
        </div>
      ) : (
        <div className="space-y-6">
          {cart.map(item => (
            <div key={item.cartId} className="flex items-center gap-6 bg-white/5 p-4 rounded-xl border border-white/10">
              <img src={item.image} className="w-24 h-24 object-cover rounded-lg" />
              <div className="flex-1">
                <h3 className="font-bold text-lg leading-tight">{item.name}</h3>
                <p className="text-sm text-red-500 font-bold tracking-widest uppercase">Size: {item.selectedSize}</p>
              </div>
              <div className="text-right">
                <p className="font-black text-xl mb-2">${item.price}</p>
                <button 
                  onClick={() => setCart(cart.filter(c => c.cartId !== item.cartId))}
                  className="text-white/30 hover:text-red-500 transition"
                ><Trash2 size={20}/></button>
              </div>
            </div>
          ))}

          <div className="mt-10 p-8 bg-white text-black rounded-2xl flex justify-between items-center">
            <div>
              <p className="text-xs font-black uppercase opacity-60">Total Amount</p>
              <p className="text-4xl font-black tracking-tighter">${total}</p>
            </div>
            <button className="bg-red-600 text-white px-10 py-4 font-black rounded-xl hover:scale-105 transition shadow-lg shadow-red-600/40 uppercase italic">
              Checkout ($5000 Limit)
            </button>
          </div>
        </div>
      )}
    </div>
  );
}
