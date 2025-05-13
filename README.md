# VICKY-SHOP
import React, { useState } from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input"; import { Textarea } from "@/components/ui/textarea";

const products = [ { id: 1, name: "Scammer Awareness Poster", price: "₹199", description: "Custom poster to educate about scams", image: "https://via.placeholder.com/300x200?text=Poster" }, { id: 2, name: "Custom Profile Photo", price: "₹149", description: "Personalized profile photo for social media", image: "https://via.placeholder.com/300x200?text=Profile+Photo" } ];

export default function HomePage() { const [customInput, setCustomInput] = useState(""); const [uploadedImage, setUploadedImage] = useState(null);

const handleImageUpload = (e) => { setUploadedImage(e.target.files[0]); };

const handleCustomizationSubmit = () => { alert("Customization submitted: " + customInput); };

return ( <div className="p-4 space-y-8"> <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4"> {products.map((product) => ( <Card key={product.id} className="rounded-2xl shadow-md"> <img src={product.image} alt={product.name} className="rounded-t-2xl w-full h-48 object-cover" /> <CardContent className="p-4"> <h2 className="text-xl font-bold">{product.name}</h2> <p className="text-gray-600 text-sm mb-2">{product.description}</p> <p className="text-lg font-semibold mb-2">{product.price}</p> <Button>Add to Cart</Button> </CardContent> </Card> ))} </div>

<div className="p-4 border rounded-2xl shadow-md">
    <h3 className="text-2xl font-bold mb-4">Customize Your Product</h3>
    <Textarea
      placeholder="Enter text or instructions for customization"
      className="mb-4"
      value={customInput}
      onChange={(e) => setCustomInput(e.target.value)}
    />
    <Input type="file" onChange={handleImageUpload} className="mb-4" />
    <Button onClick={handleCustomizationSubmit}>Submit Customization</Button>
  </div>
</div>

); }

