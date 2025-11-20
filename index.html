import React, { useState, useEffect, useRef } from 'react';
import { Send, Sprout, Cloud, DollarSign, Bug, Droplets, Sun, TrendingUp, Camera, MapPin, Bell, Book, Users, MessageSquare, X, Upload, Zap, AlertCircle, CheckCircle, Leaf, Activity } from 'lucide-react';

const AgriMitra = () => {
  const [messages, setMessages] = useState([]);
  const [input, setInput] = useState('');
  const [loading, setLoading] = useState(false);
  const [location, setLocation] = useState(null);
  const [selectedImage, setSelectedImage] = useState(null);
  const [imagePreview, setImagePreview] = useState(null);
  const [analyzing, setAnalyzing] = useState(false);
  const messagesEndRef = useRef(null);
  const fileInputRef = useRef(null);

  const scrollToBottom = () => {
    messagesEndRef.current?.scrollIntoView({ behavior: 'smooth' });
  };

  useEffect(() => {
    scrollToBottom();
  }, [messages]);

  useEffect(() => {
    setMessages([{
      role: 'assistant',
      content: '🌾 Namaste! I am AgriMitra, your AI farming assistant with advanced capabilities:\n\n📸 Upload crop/pest images for AI analysis\n🌤 Real-time weather monitoring\n💰 Live market price tracking\n🔬 Disease diagnosis & solutions\n📊 Yield prediction & optimization\n🌱 Personalized crop recommendations\n\nHow can I help you today?',
      timestamp: new Date(),
      type: 'text'
    }]);
  }, []);

  const quickActions = [
    { icon: Camera, label: 'Analyze Image', action: 'image' },
    { icon: Cloud, label: 'Weather', prompt: 'Get detailed weather forecast and farming recommendations for my location' },
    { icon: DollarSign, label: 'Market Prices', action: 'market' },
    { icon: Bug, label: 'Pest Solutions', prompt: 'Show me comprehensive pest management solutions' },
    { icon: Droplets, label: 'Irrigation Plan', prompt: 'Create an irrigation schedule based on my crop and soil type' },
    { icon: TrendingUp, label: 'Yield Optimize', prompt: 'How can I optimize my crop yield this season?' },
    { icon: Leaf, label: 'Soil Health', prompt: 'Analyze soil health requirements and provide fertilizer recommendations' },
    { icon: Activity, label: 'Crop Monitor', prompt: 'Help me set up crop health monitoring practices' }
  ];

  const handleImageUpload = (e) => {
    const file = e.target.files?.[0];
    if (file) {
      setSelectedImage(file);
      const reader = new FileReader();
      reader.onloadend = () => {
        setImagePreview(reader.result);
      };
      reader.readAsDataURL(file);
    }
  };

  const analyzeImage = async () => {
    if (!selectedImage) return;

    setAnalyzing(true);
    setLoading(true);

    try {
      const reader = new FileReader();
      reader.onloadend = async () => {
        const base64Image = reader.result.split(',')[1];
        
        const userMessage = {
          role: 'user',
          content: 'Please analyze this agricultural image',
          timestamp: new Date(),
          type: 'image',
          image: imagePreview
        };

        setMessages(prev => [...prev, userMessage]);

        const response = await fetch('https://api.anthropic.com/v1/messages', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            model: 'claude-sonnet-4-20250514',
            max_tokens: 2000,
            messages: [{
              role: 'user',
              content: [
                {
                  type: 'image',
                  source: {
                    type: 'base64',
                    media_type: selectedImage.type,
                    data: base64Image
                  }
                },
                {
                  type: 'text',
                  text: `You are AgriMitra, an expert agricultural AI assistant. Analyze this image thoroughly and provide:

1. *Identification*: What crop/plant/pest/disease is shown
2. *Health Assessment*: Current condition (healthy, stressed, diseased)
3. *Issues Detected*: Any visible problems (pests, diseases, nutrient deficiencies, etc.)
4. *Severity Level*: Rate as Low/Medium/High/Critical
5. *Immediate Actions*: What to do right now
6. *Treatment Plan*: Detailed step-by-step solution
7. *Prevention*: How to prevent this in future
8. *Timeline*: Expected recovery time
9. *Cost Estimate*: Approximate treatment cost in INR

Be specific, practical, and consider Indian farming conditions. Use simple language with both English and Hindi terms where helpful.`
                }
              ]
            }]
          })
        });

        const data = await response.json();
        const assistantMessage = data.content
          .filter(block => block.type === 'text')
          .map(block => block.text)
          .join('\n');

        setMessages(prev => [...prev, {
          role: 'assistant',
          content: assistantMessage,
          timestamp: new Date(),
          type: 'analysis'
        }]);

        setSelectedImage(null);
        setImagePreview(null);
      };

      reader.readAsDataURL(selectedImage);
    } catch (error) {
      setMessages(prev => [...prev, {
        role: 'assistant',
        content: '⚠ Error analyzing image. Please try again.',
        timestamp: new Date(),
        type: 'error'
      }]);
    } finally {
      setAnalyzing(false);
      setLoading(false);
    }
  };

  const fetchWeatherData = async () => {
    setLoading(true);
    try {
      const prompt = location 
        ? Get current weather and 7-day forecast for coordinates ${location.lat}, ${location.lng}. Provide farming-specific insights.
        : 'Get current weather forecast for major Indian agricultural regions and provide farming recommendations.';

      const response = await fetch('https://api.anthropic.com/v1/messages', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          model: 'claude-sonnet-4-20250514',
          max_tokens: 1500,
          tools: [{
            type: "web_search_20250305",
            name: "web_search"
          }],
          messages: [{
            role: 'user',
            content: prompt
          }]
        })
      });

      const data = await response.json();
      const fullResponse = data.content
        .map(item => (item.type === "text" ? item.text : ""))
        .filter(Boolean)
        .join("\n");

      setMessages(prev => [...prev, {
        role: 'assistant',
        content: 🌤 **Weather Analysis**\n\n${fullResponse},
        timestamp: new Date(),
        type: 'weather'
      }]);
    } catch (error) {
      setMessages(prev => [...prev, {
        role: 'assistant',
        content: '⚠ Unable to fetch weather data. Please try again.',
        timestamp: new Date(),
        type: 'error'
      }]);
    } finally {
      setLoading(false);
    }
  };

  const fetchMarketPrices = async () => {
    setLoading(true);
    try {
      const response = await fetch('https://api.anthropic.com/v1/messages', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          model: 'claude-sonnet-4-20250514',
          max_tokens: 1500,
          tools: [{
            type: "web_search_20250305",
            name: "web_search"
          }],
          messages: [{
            role: 'user',
            content: 'Get current market prices (mandi bhav) for major crops in India today - wheat, rice, cotton, soybean, pulses, vegetables. Include price trends and recommendations for farmers.'
          }]
        })
      });

      const data = await response.json();
      const fullResponse = data.content
        .map(item => (item.type === "text" ? item.text : ""))
        .filter(Boolean)
        .join("\n");

      setMessages(prev => [...prev, {
        role: 'assistant',
        content: 💰 **Market Prices & Trends**\n\n${fullResponse},
        timestamp: new Date(),
        type: 'market'
      }]);
    } catch (error) {
      setMessages(prev => [...prev, {
        role: 'assistant',
        content: '⚠ Unable to fetch market data. Please try again.',
        timestamp: new Date(),
        type: 'error'
      }]);
    } finally {
      setLoading(false);
    }
  };

  const handleSubmit = async (customPrompt = null) => {
    const userMessage = customPrompt || input;
    if (!userMessage.trim() || loading) return;

    const newUserMessage = {
      role: 'user',
      content: userMessage,
      timestamp: new Date(),
      type: 'text'
    };

    setMessages(prev => [...prev, newUserMessage]);
    setInput('');
    setLoading(true);

    try {
      const systemPrompt = `You are AgriMitra, an advanced AI assistant for Indian farmers with expertise in:

- Precision agriculture and modern farming techniques
- Pest & disease management with specific pesticide recommendations
- Soil science and nutrient management
- Irrigation optimization and water management
- Crop selection based on soil type, climate, and market demand
- Government schemes (PM-KISAN, PMFBY, Soil Health Card, KCC, etc.)
- Organic and sustainable farming practices
- Market analysis and price trends
- Weather interpretation for agricultural decisions
- Yield optimization strategies
- Post-harvest management
- Farm mechanization

${location ? User's location: ${location.lat}, ${location.lng} (${location.address || 'India'}) : 'User location: India'}

Provide detailed, actionable advice with:
- Specific product names when recommending pesticides/fertilizers
- Exact dosages and application methods
- Cost estimates in INR
- Timeline for implementation
- Expected outcomes
- Risk factors and precautions

Use simple language mixing English and Hindi agricultural terms. Be encouraging and practical.`;

      const response = await fetch('https://api.anthropic.com/v1/messages', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          model: 'claude-sonnet-4-20250514',
          max_tokens: 2000,
          system: systemPrompt,
          tools: [{
            type: "web_search_20250305",
            name: "web_search"
          }],
          messages: [
            ...messages.slice(-8).filter(m => m.type !== 'image').map(msg => ({
              role: msg.role,
              content: msg.content
            })),
            { role: 'user', content: userMessage }
          ]
        })
      });

      const data = await response.json();
      const assistantMessage = data.content
        .map(item => (item.type === "text" ? item.text : ""))
        .filter(Boolean)
        .join("\n");

      setMessages(prev => [...prev, {
        role: 'assistant',
        content: assistantMessage,
        timestamp: new Date(),
        type: 'text'
      }]);
    } catch (error) {
      setMessages(prev => [...prev, {
        role: 'assistant',
        content: '⚠ Sorry, I encountered an error. Please try again.',
        timestamp: new Date(),
        type: 'error'
      }]);
    } finally {
      setLoading(false);
    }
  };

  const handleQuickAction = (action) => {
    if (action.action === 'image') {
      fileInputRef.current?.click();
    } else if (action.action === 'market') {
      fetchMarketPrices();
    } else if (action.prompt) {
      handleSubmit(action.prompt);
    }
  };

  const getLocation = () => {
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(
        async (position) => {
          const loc = {
            lat: position.coords.latitude,
            lng: position.coords.longitude
          };
          
          try {
            const response = await fetch('https://api.anthropic.com/v1/messages', {
              method: 'POST',
              headers: {
                'Content-Type': 'application/json',
              },
              body: JSON.stringify({
                model: 'claude-sonnet-4-20250514',
                max_tokens: 500,
                tools: [{
                  type: "web_search_20250305",
                  name: "web_search"
                }],
                messages: [{
                  role: 'user',
                  content: Get location name and agricultural zone for coordinates ${loc.lat}, ${loc.lng} in India
                }]
              })
            });

            const data = await response.json();
            const locationInfo = data.content
              .map(item => (item.type === "text" ? item.text : ""))
              .filter(Boolean)
              .join("\n");

            loc.address = locationInfo;
            setLocation(loc);

            setMessages(prev => [...prev, {
              role: 'assistant',
              content: 📍 **Location Detected**\n\n${locationInfo}\n\nI can now provide location-specific agricultural advice!,
              timestamp: new Date(),
              type: 'system'
            }]);
          } catch {
            setLocation(loc);
            setMessages(prev => [...prev, {
              role: 'assistant',
              content: 📍 Location detected (${loc.lat.toFixed(4)}, ${loc.lng.toFixed(4)}). I can now provide location-specific advice!,
              timestamp: new Date(),
              type: 'system'
            }]);
          }
        },
        () => {
          alert('Please enable location access for personalized farming recommendations');
        }
      );
    }
  };

  return (
    <div className="flex flex-col h-screen bg-gradient-to-br from-green-50 via-emerald-50 to-teal-50">
      <div className="bg-gradient-to-r from-green-600 via-emerald-600 to-teal-600 text-white p-4 shadow-xl">
        <div className="max-w-6xl mx-auto">
          <div className="flex items-center justify-between">
            <div className="flex items-center gap-3">
              <div className="bg-white p-2 rounded-xl shadow-lg">
                <Sprout className="w-7 h-7 text-green-600" />
              </div>
              <div>
                <h1 className="text-2xl font-bold">AgriMitra AI</h1>
                <p className="text-xs text-green-100">Advanced Farming Intelligence System</p>
              </div>
            </div>
            <div className="flex items-center gap-2">
              <button
                onClick={() => fetchWeatherData()}
                className="flex items-center gap-2 bg-white/20 hover:bg-white/30 px-3 py-2 rounded-lg transition-all"
              >
                <Cloud className="w-4 h-4" />
                <span className="text-sm hidden md:inline">Weather</span>
              </button>
              <button
                onClick={getLocation}
                className="flex items-center gap-2 bg-white/20 hover:bg-white/30 px-3 py-2 rounded-lg transition-all"
              >
                <MapPin className="w-4 h-4" />
                <span className="text-sm hidden md:inline">
                  {location ? '✓ Located' : 'Enable GPS'}
                </span>
              </button>
            </div>
          </div>
        </div>
      </div>

      <div className="bg-white border-b border-green-100 p-3 shadow-md">
        <div className="max-w-6xl mx-auto">
          <div className="grid grid-cols-4 md:grid-cols-8 gap-2">
            {quickActions.map((action, idx) => (
              <button
                key={idx}
                onClick={() => handleQuickAction(action)}
                className="flex flex-col items-center gap-1 p-2 rounded-xl hover:bg-gradient-to-br hover:from-green-50 hover:to-emerald-50 transition-all group border border-transparent hover:border-green-200"
              >
                <action.icon className="w-5 h-5 text-green-600 group-hover:text-green-700 group-hover:scale-110 transition-transform" />
                <span className="text-xs text-gray-700 text-center">{action.label}</span>
              </button>
            ))}
          </div>
        </div>
      </div>

      {imagePreview && (
        <div className="bg-blue-50 border-b border-blue-200 p-3">
          <div className="max-w-6xl mx-auto flex items-center gap-3">
            <img src={imagePreview} alt="Preview" className="w-20 h-20 object-cover rounded-lg border-2 border-blue-300" />
            <div className="flex-1">
              <p className="text-sm font-semibold text-gray-800">Image ready for analysis</p>
              <p className="text-xs text-gray-600">Click "Analyze" to get AI-powered insights</p>
            </div>
            <button
              onClick={analyzeImage}
              disabled={analyzing}
              className="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 disabled:bg-gray-400 transition-colors flex items-center gap-2"
            >
              <Zap className="w-4 h-4" />
              {analyzing ? 'Analyzing...' : 'Analyze'}
            </button>
            <button
              onClick={() => {
                setImagePreview(null);
                setSelectedImage(null);
              }}
              className="text-gray-600 hover:text-red-600 transition-colors"
            >
              <X className="w-5 h-5" />
            </button>
          </div>
        </div>
      )}

      <div className="flex-1 overflow-y-auto p-4">
        <div className="max-w-6xl mx-auto space-y-4">
          {messages.map((msg, idx) => (
            <div
              key={idx}
              className={flex ${msg.role === 'user' ? 'justify-end' : 'justify-start'}}
            >
              <div
                className={`max-w-[85%] rounded-2xl p-4 shadow-lg ${
                  msg.role === 'user'
                    ? 'bg-gradient-to-br from-green-600 to-emerald-600 text-white'
                    : msg.type === 'analysis'
                    ? 'bg-gradient-to-br from-blue-50 to-indigo-50 border-2 border-blue-200'
                    : msg.type === 'weather'
                    ? 'bg-gradient-to-br from-sky-50 to-blue-50 border-2 border-sky-200'
                    : msg.type === 'market'
                    ? 'bg-gradient-to-br from-amber-50 to-yellow-50 border-2 border-amber-200'
                    : msg.type === 'system'
                    ? 'bg-gradient-to-br from-purple-50 to-pink-50 border-2 border-purple-200'
                    : 'bg-white border-2 border-green-100'
                }`}
              >
                {msg.image && (
                  <img src={msg.image} alt="Uploaded" className="w-full rounded-lg mb-3 border-2 border-white" />
                )}
                <div className="whitespace-pre-wrap text-gray-800">{msg.content}</div>
                <div className={`text-xs mt-2 flex items-center gap-2 ${
                  msg.role === 'user' ? 'text-green-100' : 'text-gray-500'
                }`}>
                  {msg.type === 'analysis' && <CheckCircle className="w-3 h-3" />}
                  {msg.type === 'weather' && <Cloud className="w-3 h-3" />}
                  {msg.type === 'market' && <DollarSign className="w-3 h-3" />}
                  {msg.timestamp.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' })}
                </div>
              </div>
            </div>
          ))}
          {loading && (
            <div className="flex justify-start">
              <div className="bg-white rounded-2xl p-4 shadow-lg border-2 border-green-100">
                <div className="flex gap-2 items-center">
                  <div className="w-2 h-2 bg-green-600 rounded-full animate-bounce"></div>
                  <div className="w-2 h-2 bg-green-600 rounded-full animate-bounce" style={{ animationDelay: '0.2s' }}></div>
                  <div className="w-2 h-2 bg-green-600 rounded-full animate-bounce" style={{ animationDelay: '0.4s' }}></div>
                  <span className="text-sm text-gray-600 ml-2">Processing...</span>
                </div>
              </div>
            </div>
          )}
          <div ref={messagesEndRef} />
        </div>
      </div>

      <div className="bg-white border-t-2 border-green-200 p-4 shadow-2xl">
        <div className="max-w-6xl mx-auto">
          <div className="flex gap-2">
            <input
              ref={fileInputRef}
              type="file"
              accept="image/*"
              onChange={handleImageUpload}
              className="hidden"
            />
            <button
              onClick={() => fileInputRef.current?.click()}
              className="bg-gradient-to-br from-blue-500 to-indigo-600 text-white p-3 rounded-xl hover:from-blue-600 hover:to-indigo-700 transition-all shadow-lg"
              title="Upload image for analysis"
            >
              <Camera className="w-5 h-5" />
            </button>
            <input
              type="text"
              value={input}
              onChange={(e) => setInput(e.target.value)}
              onKeyPress={(e) => e.key === 'Enter' && handleSubmit()}
              placeholder="Ask about crops, diseases, weather, prices, solutions..."
              className="flex-1 px-4 py-3 border-2 border-green-200 rounded-xl focus:outline-none focus:border-green-500 focus:ring-2 focus:ring-green-200 transition-all"
              disabled={loading}
            />
            <button
              onClick={() => handleSubmit()}
              disabled={loading || !input.trim()}
              className="bg-gradient-to-br from-green-600 to-emerald-600 text-white px-6 py-3 rounded-xl hover:from-green-700 hover:to-emerald-700 disabled:from-gray-300 disabled:to-gray-400 disabled:cursor-not-allowed transition-all shadow-lg"
            >
              <Send className="w-5 h-5" />
            </button>
          </div>
          <div className="mt-2 flex items-center justify-center gap-4 text-xs text-gray-500">
            <span className="flex items-center gap-1">
              <Camera className="w-3 h-3" />
              Upload crop images
            </span>
            <span>•</span>
            <span className="flex items-center gap-1">
              <Zap className="w-3 h-3" />
              AI-powered solutions
            </span>
            <span>•</span>
            <span className="flex items-center gap-1">
              <MapPin className="w-3 h-3" />
              Enable GPS for best results
            </span>
          </div>
        </div>
      </div>
    </div>
  );
};

export default AgriMitra;