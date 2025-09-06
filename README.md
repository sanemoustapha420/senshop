<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SenShop - Marketplace Sénégalais</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .gradient-bg { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .card-hover { transition: all 0.3s ease; }
        .card-hover:hover { transform: translateY(-5px); box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1); }
        .screen { display: none; }
        .screen.active { display: block; }
        .logo-animation { animation: pulse 2s infinite; }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.8; } }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Navigation -->
    <nav class="bg-white shadow-lg sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center cursor-pointer" onclick="showScreen('home')">
                    <div class="w-10 h-10 gradient-bg rounded-lg flex items-center justify-center mr-3 logo-animation">
                        <span class="text-white font-bold text-xl">S</span>
                    </div>
                    <span class="text-2xl font-bold text-gray-800">SenShop</span>
                </div>
                
                <div class="hidden md:flex items-center space-x-8">
                    <button onclick="showScreen('home')" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Accueil</button>
                    <button onclick="showScreen('products')" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Produits</button>
                    <button onclick="showScreen('seller')" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Vendre</button>
                    <button onclick="showScreen('admin')" class="nav-link text-gray-700 hover:text-purple-600 font-medium">Admin</button>
                </div>

                <div class="flex items-center space-x-4">
                    <div class="relative">
                        <button class="p-2 text-gray-600 hover:text-purple-600">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4m0 0L7 13m0 0l-2.5 5M7 13l2.5 5m6-5v6a2 2 0 11-4 0v-6m4 0V9a2 2 0 10-4 0v4.01"></path>
                            </svg>
                        </button>
                        <span class="absolute -top-2 -right-2 bg-red-500 text-white text-xs rounded-full h-5 w-5 flex items-center justify-center">3</span>
                    </div>
                    <button onclick="showScreen('login')" class="bg-purple-600 text-white px-4 py-2 rounded-lg hover:bg-purple-700 transition-colors">
                        Connexion
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Écran d'accueil -->
    <div id="home" class="screen active">
        <!-- Hero Section -->
        <div class="gradient-bg text-white py-20">
            <div class="max-w-7xl mx-auto px-4 text-center">
                <h1 class="text-5xl font-bold mb-6">Bienvenue sur SenShop</h1>
                <p class="text-xl mb-8 opacity-90">La marketplace qui connecte le Sénégal</p>
                <div class="flex justify-center space-x-4">
                    <button onclick="showScreen('products')" class="bg-white text-purple-600 px-8 py-3 rounded-lg font-semibold hover:bg-gray-100 transition-colors">
                        Explorer les produits
                    </button>
                    <button onclick="showScreen('seller')" class="border-2 border-white text-white px-8 py-3 rounded-lg font-semibold hover:bg-white hover:text-purple-600 transition-colors">
                        Commencer à vendre
                    </button>
                </div>
            </div>
        </div>

        <!-- Catégories populaires -->
        <div class="max-w-7xl mx-auto px-4 py-16">
            <h2 class="text-3xl font-bold text-center mb-12">Catégories populaires</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <div class="bg-white p-6 rounded-xl shadow-md card-hover cursor-pointer">
                    <div class="text-4xl mb-4">👕</div>
                    <h3 class="font-semibold mb-2">Mode & Vêtements</h3>
                    <p class="text-gray-600 text-sm">Découvrez la mode sénégalaise</p>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md card-hover cursor-pointer">
                    <div class="text-4xl mb-4">📱</div>
                    <h3 class="font-semibold mb-2">Électronique</h3>
                    <p class="text-gray-600 text-sm">Smartphones, ordinateurs...</p>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md card-hover cursor-pointer">
                    <div class="text-4xl mb-4">🏠</div>
                    <h3 class="font-semibold mb-2">Maison & Jardin</h3>
                    <p class="text-gray-600 text-sm">Tout pour votre foyer</p>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md card-hover cursor-pointer">
                    <div class="text-4xl mb-4">🍽️</div>
                    <h3 class="font-semibold mb-2">Alimentation</h3>
                    <p class="text-gray-600 text-sm">Produits locaux et frais</p>
                </div>
            </div>
        </div>

        <!-- Statistiques -->
        <div class="bg-gray-100 py-16">
            <div class="max-w-7xl mx-auto px-4">
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
                    <div>
                        <div class="text-4xl font-bold text-purple-600 mb-2">10,000+</div>
                        <div class="text-gray-600">Produits disponibles</div>
                    </div>
                    <div>
                        <div class="text-4xl font-bold text-purple-600 mb-2">5,000+</div>
                        <div class="text-gray-600">Vendeurs actifs</div>
                    </div>
                    <div>
                        <div class="text-4xl font-bold text-purple-600 mb-2">50,000+</div>
                        <div class="text-gray-600">Clients satisfaits</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Écran Produits -->
    <div id="products" class="screen">
        <div class="max-w-7xl mx-auto px-4 py-8">
            <div class="flex justify-between items-center mb-8">
                <h1 class="text-3xl font-bold">Tous les produits</h1>
                <div class="flex space-x-4">
                    <select class="border rounded-lg px-4 py-2">
                        <option>Toutes catégories</option>
                        <option>Mode</option>
                        <option>Électronique</option>
                        <option>Maison</option>
                    </select>
                    <select class="border rounded-lg px-4 py-2">
                        <option>Prix croissant</option>
                        <option>Prix décroissant</option>
                        <option>Plus récents</option>
                    </select>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <div class="bg-white rounded-xl shadow-md overflow-hidden card-hover">
                    <div class="h-48 bg-gradient-to-br from-purple-400 to-pink-400"></div>
                    <div class="p-4">
                        <h3 class="font-semibold mb-2">Boubou Traditionnel</h3>
                        <p class="text-gray-600 text-sm mb-2">Vêtement traditionnel sénégalais</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-purple-600">25,000 FCFA</span>
                            <button onclick="addToCartAndPay()" class="bg-purple-600 text-white px-3 py-1 rounded-lg text-sm hover:bg-purple-700">
                                Ajouter
                            </button>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-md overflow-hidden card-hover">
                    <div class="h-48 bg-gradient-to-br from-blue-400 to-cyan-400"></div>
                    <div class="p-4">
                        <h3 class="font-semibold mb-2">Smartphone Samsung</h3>
                        <p class="text-gray-600 text-sm mb-2">Galaxy A54 - Neuf</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-purple-600">180,000 FCFA</span>
                            <button onclick="addToCartAndPay()" class="bg-purple-600 text-white px-3 py-1 rounded-lg text-sm hover:bg-purple-700">
                                Ajouter
                            </button>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-md overflow-hidden card-hover">
                    <div class="h-48 bg-gradient-to-br from-green-400 to-emerald-400"></div>
                    <div class="p-4">
                        <h3 class="font-semibold mb-2">Riz Local Premium</h3>
                        <p class="text-gray-600 text-sm mb-2">Sac de 25kg - Vallée du fleuve</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-purple-600">12,500 FCFA</span>
                            <button onclick="addToCartAndPay()" class="bg-purple-600 text-white px-3 py-1 rounded-lg text-sm hover:bg-purple-700">
                                Ajouter
                            </button>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-md overflow-hidden card-hover">
                    <div class="h-48 bg-gradient-to-br from-orange-400 to-red-400"></div>
                    <div class="p-4">
                        <h3 class="font-semibold mb-2">Canapé 3 places</h3>
                        <p class="text-gray-600 text-sm mb-2">Cuir véritable - Très bon état</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-purple-600">85,000 FCFA</span>
                            <button onclick="addToCartAndPay()" class="bg-purple-600 text-white px-3 py-1 rounded-lg text-sm hover:bg-purple-700">
                                Ajouter
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Écran Vendeur -->
    <div id="seller" class="screen">
        <div class="max-w-4xl mx-auto px-4 py-8">
            <h1 class="text-3xl font-bold mb-8">Espace Vendeur</h1>
            
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                <!-- Statistiques vendeur -->
                <div class="lg:col-span-1">
                    <div class="bg-white rounded-xl shadow-md p-6 mb-6">
                        <h2 class="text-xl font-semibold mb-4">Mes statistiques</h2>
                        <div class="space-y-4">
                            <div class="flex justify-between">
                                <span class="text-gray-600">Produits actifs</span>
                                <span class="font-semibold">12</span>
                            </div>
                            <div class="flex justify-between">
                                <span class="text-gray-600">Ventes ce mois</span>
                                <span class="font-semibold">28</span>
                            </div>
                            <div class="flex justify-between">
                                <span class="text-gray-600">Chiffre d'affaires</span>
                                <span class="font-semibold text-green-600">450,000 FCFA</span>
                            </div>
                        </div>
                    </div>

                    <div class="bg-white rounded-xl shadow-md p-6">
                        <h2 class="text-xl font-semibold mb-4">Actions rapides</h2>
                        <div class="space-y-3">
                            <button class="w-full bg-purple-600 text-white py-2 rounded-lg hover:bg-purple-700">
                                Ajouter un produit
                            </button>
                            <button class="w-full border border-purple-600 text-purple-600 py-2 rounded-lg hover:bg-purple-50">
                                Gérer les commandes
                            </button>
                            <button class="w-full border border-gray-300 text-gray-700 py-2 rounded-lg hover:bg-gray-50">
                                Voir les statistiques
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Formulaire d'ajout de produit -->
                <div class="lg:col-span-2">
                    <div class="bg-white rounded-xl shadow-md p-6">
                        <h2 class="text-xl font-semibold mb-6">Ajouter un nouveau produit</h2>
                        <form class="space-y-4">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Nom du produit</label>
                                <input type="text" class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-purple-500" placeholder="Ex: Boubou traditionnel">
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-2">Catégorie</label>
                                    <select class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-purple-500">
                                        <option>Mode & Vêtements</option>
                                        <option>Électronique</option>
                                        <option>Maison & Jardin</option>
                                        <option>Alimentation</option>
                                    </select>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-2">Prix (FCFA)</label>
                                    <input type="number" class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-purple-500" placeholder="25000">
                                </div>
                            </div>

                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Description</label>
                                <textarea rows="4" class="w-full border border-gray-300 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-purple-500" placeholder="Décrivez votre produit..."></textarea>
                            </div>

                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Photos du produit</label>
                                <div class="border-2 border-dashed border-gray-300 rounded-lg p-6 text-center">
                                    <div class="text-gray-400 mb-2">
                                        <svg class="mx-auto h-12 w-12" stroke="currentColor" fill="none" viewBox="0 0 48 48">
                                            <path d="M28 8H12a4 4 0 00-4 4v20m32-12v8m0 0v8a4 4 0 01-4 4H12a4 4 0 01-4-4v-4m32-4l-3.172-3.172a4 4 0 00-5.656 0L28 28M8 32l9.172-9.172a4 4 0 015.656 0L28 28m0 0l4 4m4-24h8m-4-4v8m-12 4h.02" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                                        </svg>
                                    </div>
                                    <p class="text-sm text-gray-600">Cliquez pour ajouter des photos ou glissez-déposez</p>
                                </div>
                            </div>

                            <button type="submit" class="w-full bg-purple-600 text-white py-3 rounded-lg font-semibold hover:bg-purple-700 transition-colors">
                                Publier le produit
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Écran de Connexion -->
    <div id="login" class="screen">
        <div class="min-h-screen bg-gradient-to-br from-purple-50 to-blue-50 flex items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
            <div class="max-w-md w-full space-y-8">
                <div class="text-center">
                    <div class="w-16 h-16 gradient-bg rounded-full flex items-center justify-center mx-auto mb-4">
                        <span class="text-white font-bold text-2xl">S</span>
                    </div>
                    <h2 class="text-3xl font-bold text-gray-900 mb-2">Connexion à SenShop</h2>
                    <p class="text-gray-600">Accédez à votre compte pour continuer vos achats</p>
                </div>

                <div class="bg-white rounded-2xl shadow-xl p-8">
                    <form class="space-y-6">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Adresse email</label>
                            <input type="email" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all" placeholder="votre@email.com">
                        </div>

                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Mot de passe</label>
                            <div class="relative">
                                <input type="password" id="password" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all pr-12" placeholder="••••••••">
                                <button type="button" onclick="togglePassword()" class="absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400 hover:text-gray-600">
                                    <svg id="eye-icon" class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path>
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"></path>
                                    </svg>
                                </button>
                            </div>
                        </div>

                        <div class="flex items-center justify-between">
                            <div class="flex items-center">
                                <input type="checkbox" class="h-4 w-4 text-purple-600 focus:ring-purple-500 border-gray-300 rounded">
                                <label class="ml-2 block text-sm text-gray-700">Se souvenir de moi</label>
                            </div>
                            <a href="#" class="text-sm text-purple-600 hover:text-purple-500">Mot de passe oublié ?</a>
                        </div>

                        <button type="submit" onclick="simulateLogin()" class="w-full bg-purple-600 text-white py-3 px-4 rounded-lg font-semibold hover:bg-purple-700 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:ring-offset-2 transition-all transform hover:scale-105">
                            Se connecter
                        </button>

                        <div class="relative my-6">
                            <div class="absolute inset-0 flex items-center">
                                <div class="w-full border-t border-gray-300"></div>
                            </div>
                            <div class="relative flex justify-center text-sm">
                                <span class="px-2 bg-white text-gray-500">Ou continuer avec</span>
                            </div>
                        </div>

                        <div class="grid grid-cols-2 gap-3">
                            <button type="button" class="w-full inline-flex justify-center py-3 px-4 border border-gray-300 rounded-lg shadow-sm bg-white text-sm font-medium text-gray-500 hover:bg-gray-50 transition-all">
                                <svg class="w-5 h-5 text-red-500" viewBox="0 0 24 24">
                                    <path fill="currentColor" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
                                    <path fill="currentColor" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
                                    <path fill="currentColor" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z"/>
                                    <path fill="currentColor" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"/>
                                </svg>
                                <span class="ml-2">Google</span>
                            </button>
                            <button type="button" class="w-full inline-flex justify-center py-3 px-4 border border-gray-300 rounded-lg shadow-sm bg-white text-sm font-medium text-gray-500 hover:bg-gray-50 transition-all">
                                <svg class="w-5 h-5 text-blue-600" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                                </svg>
                                <span class="ml-2">Facebook</span>
                            </button>
                        </div>

                        <p class="text-center text-sm text-gray-600">
                            Pas encore de compte ? 
                            <a href="#" class="font-medium text-purple-600 hover:text-purple-500">Créer un compte</a>
                        </p>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <!-- Écran de Paiement -->
    <div id="payment" class="screen">
        <div class="min-h-screen bg-gradient-to-br from-purple-50 via-blue-50 to-indigo-50 py-8">
            <div class="max-w-6xl mx-auto px-4">
                <!-- En-tête avec progression -->
                <div class="mb-8">
                    <button onclick="showScreen('products')" class="flex items-center text-purple-600 hover:text-purple-700 mb-6 transition-colors">
                        <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
                        </svg>
                        Retour aux produits
                    </button>
                    
                    <div class="text-center mb-8">
                        <h1 class="text-4xl font-bold text-gray-900 mb-4">Finaliser votre commande</h1>
                        <p class="text-gray-600 text-lg">Quelques étapes simples pour recevoir vos produits</p>
                    </div>

                    <!-- Barre de progression -->
                    <div class="flex items-center justify-center mb-8">
                        <div class="flex items-center space-x-4">
                            <div class="flex items-center">
                                <div class="w-10 h-10 bg-purple-600 text-white rounded-full flex items-center justify-center font-bold">1</div>
                                <span class="ml-2 text-purple-600 font-medium">Livraison</span>
                            </div>
                            <div class="w-16 h-1 bg-purple-200 rounded"></div>
                            <div class="flex items-center">
                                <div class="w-10 h-10 bg-gray-300 text-gray-600 rounded-full flex items-center justify-center font-bold">2</div>
                                <span class="ml-2 text-gray-500 font-medium">Paiement</span>
                            </div>
                            <div class="w-16 h-1 bg-gray-200 rounded"></div>
                            <div class="flex items-center">
                                <div class="w-10 h-10 bg-gray-300 text-gray-600 rounded-full flex items-center justify-center font-bold">3</div>
                                <span class="ml-2 text-gray-500 font-medium">Confirmation</span>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                    <!-- Formulaire de paiement -->
                    <div class="lg:col-span-2 space-y-8">
                        <!-- Informations de livraison -->
                        <div class="bg-white rounded-2xl shadow-xl p-8 border border-purple-100">
                            <div class="flex items-center mb-6">
                                <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-blue-500 text-white rounded-xl flex items-center justify-center mr-4">
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
                                    </svg>
                                </div>
                                <div>
                                    <h2 class="text-2xl font-bold text-gray-900">Adresse de livraison</h2>
                                    <p class="text-gray-600">Où souhaitez-vous recevoir votre commande ?</p>
                                </div>
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div>
                                    <label class="block text-sm font-semibold text-gray-700 mb-3">Prénom *</label>
                                    <input type="text" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all" placeholder="Amadou" value="Amadou">
                                </div>
                                <div>
                                    <label class="block text-sm font-semibold text-gray-700 mb-3">Nom *</label>
                                    <input type="text" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all" placeholder="Diallo" value="Diallo">
                                </div>
                                <div class="md:col-span-2">
                                    <label class="block text-sm font-semibold text-gray-700 mb-3">Adresse complète *</label>
                                    <input type="text" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all" placeholder="Rue 10, Quartier Almadies" value="Rue 15, Quartier Almadies">
                                </div>
                                <div>
                                    <label class="block text-sm font-semibold text-gray-700 mb-3">Région/Ville *</label>
                                    <select class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all">
                                        <option>Dakar</option>
                                        <option>Thiès</option>
                                        <option>Saint-Louis</option>
                                        <option>Kaolack</option>
                                        <option>Ziguinchor</option>
                                        <option>Tambacounda</option>
                                        <option>Kolda</option>
                                        <option>Sédhiou</option>
                                        <option>Matam</option>
                                        <option>Kaffrine</option>
                                        <option>Kédougou</option>
                                        <option>Louga</option>
                                        <option>Fatick</option>
                                        <option>Diourbel</option>
                                    </select>
                                </div>
                                <div>
                                    <label class="block text-sm font-semibold text-gray-700 mb-3">Téléphone *</label>
                                    <input type="tel" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all" placeholder="+221 77 123 45 67" value="+221 77 123 45 67">
                                </div>
                                <div class="md:col-span-2">
                                    <label class="block text-sm font-semibold text-gray-700 mb-3">Instructions de livraison (optionnel)</label>
                                    <textarea class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent transition-all" rows="3" placeholder="Ex: Sonner à l'interphone, 2ème étage..."></textarea>
                                </div>
                            </div>

                            <!-- Options de livraison -->
                            <div class="mt-8">
                                <h3 class="text-lg font-semibold text-gray-900 mb-4">Options de livraison</h3>
                                <div class="space-y-3">
                                    <div class="border-2 border-purple-200 bg-purple-50 rounded-xl p-4 cursor-pointer">
                                        <label class="flex items-center cursor-pointer">
                                            <input type="radio" name="delivery" value="standard" class="text-purple-600 focus:ring-purple-500" checked>
                                            <div class="ml-4 flex-1">
                                                <div class="flex justify-between items-center">
                                                    <div>
                                                        <p class="font-semibold text-gray-900">Livraison standard</p>
                                                        <p class="text-sm text-gray-600">2-3 jours ouvrables</p>
                                                    </div>
                                                    <span class="font-bold text-purple-600">2,500 FCFA</span>
                                                </div>
                                            </div>
                                        </label>
                                    </div>
                                    <div class="border-2 border-gray-200 rounded-xl p-4 cursor-pointer hover:border-purple-200 transition-colors">
                                        <label class="flex items-center cursor-pointer">
                                            <input type="radio" name="delivery" value="express" class="text-purple-600 focus:ring-purple-500">
                                            <div class="ml-4 flex-1">
                                                <div class="flex justify-between items-center">
                                                    <div>
                                                        <p class="font-semibold text-gray-900">Livraison express</p>
                                                        <p class="text-sm text-gray-600">24h dans Dakar</p>
                                                    </div>
                                                    <span class="font-bold text-gray-900">5,000 FCFA</span>
                                                </div>
                                            </div>
                                        </label>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Mode de paiement -->
                        <div class="bg-white rounded-2xl shadow-xl p-8 border border-purple-100">
                            <div class="flex items-center mb-6">
                                <div class="w-12 h-12 bg-gradient-to-r from-green-500 to-blue-500 text-white rounded-xl flex items-center justify-center mr-4">
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10h18M7 15h1m4 0h1m-7 4h12a3 3 0 003-3V8a3 3 0 00-3-3H6a3 3 0 00-3 3v8a3 3 0 003 3z"></path>
                                    </svg>
                                </div>
                                <div>
                                    <h2 class="text-2xl font-bold text-gray-900">Mode de paiement</h2>
                                    <p class="text-gray-600">Choisissez votre méthode de paiement préférée</p>
                                </div>
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <!-- Orange Money -->
                                <div class="border-2 border-gray-200 rounded-xl p-6 hover:border-orange-300 cursor-pointer transition-all hover:shadow-lg">
                                    <label class="flex flex-col items-center cursor-pointer">
                                        <input type="radio" name="payment" value="orange" class="text-orange-600 focus:ring-orange-500 mb-3">
                                        <div class="w-16 h-12 bg-gradient-to-r from-orange-500 to-orange-600 rounded-lg flex items-center justify-center mb-3">
                                            <span class="text-white font-bold text-lg">OM</span>
                                        </div>
                                        <p class="font-semibold text-gray-900 text-center">Orange Money</p>
                                        <p class="text-sm text-gray-600 text-center mt-1">Paiement mobile sécurisé</p>
                                        <div class="mt-3 text-xs text-green-600 bg-green-50 px-2 py-1 rounded-full">
                                            ✓ Instantané
                                        </div>
                                    </label>
                                </div>

                                <!-- Wave -->
                                <div class="border-2 border-gray-200 rounded-xl p-6 hover:border-blue-300 cursor-pointer transition-all hover:shadow-lg">
                                    <label class="flex flex-col items-center cursor-pointer">
                                        <input type="radio" name="payment" value="wave" class="text-blue-600 focus:ring-blue-500 mb-3">
                                        <div class="w-16 h-12 bg-gradient-to-r from-blue-500 to-blue-600 rounded-lg flex items-center justify-center mb-3">
                                            <span class="text-white font-bold text-lg">W</span>
                                        </div>
                                        <p class="font-semibold text-gray-900 text-center">Wave</p>
                                        <p class="text-sm text-gray-600 text-center mt-1">Transfert d'argent rapide</p>
                                        <div class="mt-3 text-xs text-green-600 bg-green-50 px-2 py-1 rounded-full">
                                            ✓ Sans frais
                                        </div>
                                    </label>
                                </div>

                                <!-- Free Money -->
                                <div class="border-2 border-gray-200 rounded-xl p-6 hover:border-red-300 cursor-pointer transition-all hover:shadow-lg">
                                    <label class="flex flex-col items-center cursor-pointer">
                                        <input type="radio" name="payment" value="free" class="text-red-600 focus:ring-red-500 mb-3">
                                        <div class="w-16 h-12 bg-gradient-to-r from-red-500 to-red-600 rounded-lg flex items-center justify-center mb-3">
                                            <span class="text-white font-bold text-lg">FM</span>
                                        </div>
                                        <p class="font-semibold text-gray-900 text-center">Free Money</p>
                                        <p class="text-sm text-gray-600 text-center mt-1">Solution de paiement Free</p>
                                        <div class="mt-3 text-xs text-blue-600 bg-blue-50 px-2 py-1 rounded-full">
                                            ✓ Sécurisé
                                        </div>
                                    </label>
                                </div>

                                <!-- Paiement à la livraison -->
                                <div class="border-2 border-green-200 bg-green-50 rounded-xl p-6 cursor-pointer transition-all">
                                    <label class="flex flex-col items-center cursor-pointer">
                                        <input type="radio" name="payment" value="cash" class="text-green-600 focus:ring-green-500 mb-3" checked>
                                        <div class="w-16 h-12 bg-gradient-to-r from-green-500 to-green-600 rounded-lg flex items-center justify-center mb-3">
                                            <span class="text-white text-2xl">💰</span>
                                        </div>
                                        <p class="font-semibold text-gray-900 text-center">Paiement à la livraison</p>
                                        <p class="text-sm text-gray-600 text-center mt-1">Payez en espèces lors de la réception</p>
                                        <div class="mt-3 text-xs text-green-600 bg-green-100 px-2 py-1 rounded-full">
                                            ✓ Recommandé
                                        </div>
                                    </label>
                                </div>
                            </div>

                            <!-- Code promo -->
                            <div class="mt-8 p-6 bg-gray-50 rounded-xl">
                                <h3 class="font-semibold text-gray-900 mb-3">Code promo ou bon de réduction</h3>
                                <div class="flex space-x-3">
                                    <input type="text" class="flex-1 px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent" placeholder="Entrez votre code">
                                    <button class="bg-purple-600 text-white px-6 py-3 rounded-xl font-semibold hover:bg-purple-700 transition-colors">
                                        Appliquer
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Bouton de confirmation -->
                        <div class="text-center">
                            <button onclick="processPayment()" class="w-full bg-gradient-to-r from-purple-600 to-blue-600 text-white py-5 px-8 rounded-2xl font-bold text-xl hover:from-purple-700 hover:to-blue-700 focus:outline-none focus:ring-4 focus:ring-purple-300 transition-all transform hover:scale-105 shadow-xl">
                                <span class="flex items-center justify-center">
                                    <svg class="w-6 h-6 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                                    </svg>
                                    Confirmer ma commande
                                </span>
                            </button>
                            <p class="text-sm text-gray-500 mt-3">
                                🔒 Paiement 100% sécurisé • Livraison garantie
                            </p>
                        </div>
                    </div>

                    <!-- Résumé de commande -->
                    <div class="lg:col-span-1">
                        <div class="bg-white rounded-2xl shadow-xl p-8 sticky top-24 border border-purple-100">
                            <h2 class="text-2xl font-bold text-gray-900 mb-6 flex items-center">
                                <svg class="w-6 h-6 mr-3 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path>
                                </svg>
                                Votre commande
                            </h2>
                            
                            <div class="space-y-6 mb-8">
                                <div class="flex items-center space-x-4 p-4 bg-purple-50 rounded-xl">
                                    <div class="w-20 h-20 bg-gradient-to-br from-purple-400 to-pink-400 rounded-xl flex items-center justify-center">
                                        <span class="text-white text-2xl">👕</span>
                                    </div>
                                    <div class="flex-1">
                                        <p class="font-semibold text-gray-900">Boubou Traditionnel</p>
                                        <p class="text-sm text-gray-600">Taille: L • Couleur: Bleu</p>
                                        <div class="flex items-center justify-between mt-2">
                                            <div class="flex items-center space-x-2">
                                                <button class="w-8 h-8 bg-white border border-gray-300 rounded-lg flex items-center justify-center text-gray-600 hover:bg-gray-50">-</button>
                                                <span class="font-semibold">1</span>
                                                <button class="w-8 h-8 bg-white border border-gray-300 rounded-lg flex items-center justify-center text-gray-600 hover:bg-gray-50">+</button>
                                            </div>
                                            <p class="text-purple-600 font-bold">25,000 FCFA</p>
                                        </div>
                                    </div>
                                </div>

                                <div class="flex items-center space-x-4 p-4 bg-green-50 rounded-xl">
                                    <div class="w-20 h-20 bg-gradient-to-br from-green-400 to-emerald-400 rounded-xl flex items-center justify-center">
                                        <span class="text-white text-2xl">🌾</span>
                                    </div>
                                    <div class="flex-1">
                                        <p class="font-semibold text-gray-900">Riz Local Premium</p>
                                        <p class="text-sm text-gray-600">Sac 25kg • Vallée du fleuve</p>
                                        <div class="flex items-center justify-between mt-2">
                                            <div class="flex items-center space-x-2">
                                                <button class="w-8 h-8 bg-white border border-gray-300 rounded-lg flex items-center justify-center text-gray-600 hover:bg-gray-50">-</button>
                                                <span class="font-semibold">2</span>
                                                <button class="w-8 h-8 bg-white border border-gray-300 rounded-lg flex items-center justify-center text-gray-600 hover:bg-gray-50">+</button>
                                            </div>
                                            <p class="text-purple-600 font-bold">25,000 FCFA</p>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <!-- Calculs -->
                            <div class="border-t-2 border-gray-100 pt-6 space-y-4">
                                <div class="flex justify-between text-gray-600">
                                    <span>Sous-total (3 articles)</span>
                                    <span class="font-semibold">50,000 FCFA</span>
                                </div>
                                <div class="flex justify-between text-gray-600">
                                    <span>Livraison standard</span>
                                    <span class="font-semibold">2,500 FCFA</span>
                                </div>
                                <div class="flex justify-between text-gray-600">
                                    <span>TVA (18%)</span>
                                    <span class="font-semibold">9,450 FCFA</span>
                                </div>
                                <div class="flex justify-between text-green-600">
                                    <span>Réduction fidélité (-5%)</span>
                                    <span class="font-semibold">-2,500 FCFA</span>
                                </div>
                                <div class="border-t-2 border-purple-100 pt-4 flex justify-between font-bold text-xl">
                                    <span class="text-gray-900">Total à payer</span>
                                    <span class="text-purple-600">59,450 FCFA</span>
                                </div>
                            </div>

                            <!-- Avantages -->
                            <div class="mt-8 space-y-3">
                                <div class="flex items-center p-3 bg-green-50 rounded-lg">
                                    <svg class="w-5 h-5 text-green-600 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                                    </svg>
                                    <span class="text-sm text-green-800 font-medium">Livraison gratuite dès 75,000 FCFA</span>
                                </div>
                                <div class="flex items-center p-3 bg-blue-50 rounded-lg">
                                    <svg class="w-5 h-5 text-blue-600 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"></path>
                                    </svg>
                                    <span class="text-sm text-blue-800 font-medium">Paiement 100% sécurisé</span>
                                </div>
                                <div class="flex items-center p-3 bg-purple-50 rounded-lg">
                                    <svg class="w-5 h-5 text-purple-600 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path>
                                    </svg>
                                    <span class="text-sm text-purple-800 font-medium">Garantie satisfaction 30 jours</span>
                                </div>
                            </div>

                            <!-- Support client -->
                            <div class="mt-8 p-4 bg-gray-50 rounded-xl text-center">
                                <p class="text-sm text-gray-600 mb-2">Besoin d'aide ?</p>
                                <div class="flex justify-center space-x-4">
                                    <button class="text-purple-600 hover:text-purple-700 text-sm font-medium">
                                        💬 Chat
                                    </button>
                                    <button class="text-purple-600 hover:text-purple-700 text-sm font-medium">
                                        📞 +221 33 123 45 67
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Écran Admin -->
    <div id="admin" class="screen">
        <div class="max-w-7xl mx-auto px-4 py-8">
            <h1 class="text-3xl font-bold mb-8">Tableau de bord Administrateur</h1>
            
            <!-- Métriques principales -->
            <div class="grid grid-cols-1 md:grid-cols-4 gap-6 mb-8">
                <div class="bg-white rounded-xl shadow-md p-6">
                    <div class="flex items-center">
                        <div class="p-3 rounded-full bg-blue-100 text-blue-600 mr-4">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197m13.5-9a2.5 2.5 0 11-5 0 2.5 2.5 0 015 0z"></path>
                            </svg>
                        </div>
                        <div>
                            <p class="text-sm text-gray-600">Utilisateurs</p>
                            <p class="text-2xl font-bold">15,247</p>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-md p-6">
                    <div class="flex items-center">
                        <div class="p-3 rounded-full bg-green-100 text-green-600 mr-4">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path>
                            </svg>
                        </div>
                        <div>
                            <p class="text-sm text-gray-600">Commandes</p>
                            <p class="text-2xl font-bold">3,891</p>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-md p-6">
                    <div class="flex items-center">
                        <div class="p-3 rounded-full bg-purple-100 text-purple-600 mr-4">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4"></path>
                            </svg>
                        </div>
                        <div>
                            <p class="text-sm text-gray-600">Produits</p>
                            <p class="text-2xl font-bold">12,456</p>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-md p-6">
                    <div class="flex items-center">
                        <div class="p-3 rounded-full bg-yellow-100 text-yellow-600 mr-4">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1"></path>
                            </svg>
                        </div>
                        <div>
                            <p class="text-sm text-gray-600">Revenus (FCFA)</p>
                            <p class="text-2xl font-bold">2.4M</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Gestion des utilisateurs et produits -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                <div class="bg-white rounded-xl shadow-md p-6">
                    <h2 class="text-xl font-semibold mb-4">Utilisateurs récents</h2>
                    <div class="space-y-4">
                        <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                            <div class="flex items-center">
                                <div class="w-10 h-10 bg-purple-500 rounded-full flex items-center justify-center text-white font-semibold mr-3">
                                    AM
                                </div>
                                <div>
                                    <p class="font-medium">Amadou Diallo</p>
                                    <p class="text-sm text-gray-600">Vendeur - Dakar</p>
                                </div>
                            </div>
                            <div class="flex space-x-2">
                                <button class="text-green-600 hover:bg-green-50 p-1 rounded">✓</button>
                                <button class="text-red-600 hover:bg-red-50 p-1 rounded">✗</button>
                            </div>
                        </div>

                        <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                            <div class="flex items-center">
                                <div class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center text-white font-semibold mr-3">
                                    FS
                                </div>
                                <div>
                                    <p class="font-medium">Fatou Sall</p>
                                    <p class="text-sm text-gray-600">Acheteur - Thiès</p>
                                </div>
                            </div>
                            <div class="flex space-x-2">
                                <button class="text-green-600 hover:bg-green-50 p-1 rounded">✓</button>
                                <button class="text-red-600 hover:bg-red-50 p-1 rounded">✗</button>
                            </div>
                        </div>

                        <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                            <div class="flex items-center">
                                <div class="w-10 h-10 bg-green-500 rounded-full flex items-center justify-center text-white font-semibold mr-3">
                                    MN
                                </div>
                                <div>
                                    <p class="font-medium">Moussa Ndiaye</p>
                                    <p class="text-sm text-gray-600">Vendeur - Saint-Louis</p>
                                </div>
                            </div>
                            <div class="flex space-x-2">
                                <button class="text-green-600 hover:bg-green-50 p-1 rounded">✓</button>
                                <button class="text-red-600 hover:bg-red-50 p-1 rounded">✗</button>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-md p-6">
                    <h2 class="text-xl font-semibold mb-4">Produits en attente</h2>
                    <div class="space-y-4">
                        <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                            <div>
                                <p class="font-medium">Boubou Grand Boubou</p>
                                <p class="text-sm text-gray-600">Mode - 35,000 FCFA</p>
                            </div>
                            <div class="flex space-x-2">
                                <button class="bg-green-500 text-white px-3 py-1 rounded text-sm hover:bg-green-600">
                                    Approuver
                                </button>
                                <button class="bg-red-500 text-white px-3 py-1 rounded text-sm hover:bg-red-600">
                                    Rejeter
                                </button>
                            </div>
                        </div>

                        <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                            <div>
                                <p class="font-medium">iPhone 13 Pro</p>
                                <p class="text-sm text-gray-600">Électronique - 450,000 FCFA</p>
                            </div>
                            <div class="flex space-x-2">
                                <button class="bg-green-500 text-white px-3 py-1 rounded text-sm hover:bg-green-600">
                                    Approuver
                                </button>
                                <button class="bg-red-500 text-white px-3 py-1 rounded text-sm hover:bg-red-600">
                                    Rejeter
                                </button>
                            </div>
                        </div>

                        <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                            <div>
                                <p class="font-medium">Thiéboudienne Kit</p>
                                <p class="text-sm text-gray-600">Alimentation - 8,500 FCFA</p>
                            </div>
                            <div class="flex space-x-2">
                                <button class="bg-green-500 text-white px-3 py-1 rounded text-sm hover:bg-green-600">
                                    Approuver
                                </button>
                                <button class="bg-red-500 text-white px-3 py-1 rounded text-sm hover:bg-red-600">
                                    Rejeter
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function showScreen(screenName) {
            // Masquer tous les écrans
            const screens = document.querySelectorAll('.screen');
            screens.forEach(screen => screen.classList.remove('active'));
            
            // Afficher l'écran demandé
            document.getElementById(screenName).classList.add('active');
            
            // Mettre à jour la navigation
            const navLinks = document.querySelectorAll('.nav-link');
            navLinks.forEach(link => link.classList.remove('text-purple-600', 'font-semibold'));
            
            // Faire défiler vers le haut
            window.scrollTo(0, 0);
        }

        // Animation du logo au chargement
        document.addEventListener('DOMContentLoaded', function() {
            const logo = document.querySelector('.logo-animation');
            setTimeout(() => {
                logo.style.animation = 'none';
            }, 4000);
        });

        // Fonctions de connexion et paiement
        function togglePassword() {
            const passwordInput = document.getElementById('password');
            const eyeIcon = document.getElementById('eye-icon');
            
            if (passwordInput.type === 'password') {
                passwordInput.type = 'text';
                eyeIcon.innerHTML = '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13.875 18.825A10.05 10.05 0 0112 19c-4.478 0-8.268-2.943-9.543-7a9.97 9.97 0 011.563-3.029m5.858.908a3 3 0 114.243 4.243M9.878 9.878l4.242 4.242M9.878 9.878L8.464 8.464m1.414 1.414L8.464 8.464m5.656 5.656l1.415 1.415m-1.415-1.415l1.415 1.415"></path>';
            } else {
                passwordInput.type = 'password';
                eyeIcon.innerHTML = '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"></path>';
            }
        }

        function simulateLogin() {
            event.preventDefault();
            const button = event.target;
            const originalText = button.textContent;
            
            button.textContent = 'Connexion en cours...';
            button.disabled = true;
            
            setTimeout(() => {
                button.textContent = 'Connecté ✓';
                button.classList.add('bg-green-600');
                button.classList.remove('bg-purple-600');
                
                setTimeout(() => {
                    showScreen('home');
                    button.textContent = originalText;
                    button.disabled = false;
                    button.classList.remove('bg-green-600');
                    button.classList.add('bg-purple-600');
                }, 1000);
            }, 1500);
        }

        function addToCartAndPay() {
            const button = event.target;
            button.textContent = 'Ajouté ✓';
            button.classList.add('bg-green-500', 'hover:bg-green-600');
            button.classList.remove('bg-purple-600', 'hover:bg-purple-700');
            
            setTimeout(() => {
                showScreen('payment');
                button.textContent = 'Ajouter';
                button.classList.remove('bg-green-500', 'hover:bg-green-600');
                button.classList.add('bg-purple-600', 'hover:bg-purple-700');
            }, 1000);
        }

        function processPayment() {
            const button = event.target;
            const originalText = button.textContent;
            
            button.textContent = 'Traitement en cours...';
            button.disabled = true;
            button.classList.add('bg-yellow-600');
            button.classList.remove('bg-purple-600');
            
            setTimeout(() => {
                button.textContent = 'Commande confirmée ✓';
                button.classList.remove('bg-yellow-600');
                button.classList.add('bg-green-600');
                
                setTimeout(() => {
                    alert('🎉 Votre commande a été confirmée ! Vous recevrez un SMS de confirmation sous peu.');
                    showScreen('home');
                    button.textContent = originalText;
                    button.disabled = false;
                    button.classList.remove('bg-green-600');
                    button.classList.add('bg-purple-600');
                }, 2000);
            }, 2000);
        }

        // Simulation d'ajout au panier pour les anciens boutons
        document.addEventListener('click', function(e) {
            if (e.target.textContent === 'Ajouter' && !e.target.onclick) {
                e.target.textContent = 'Ajouté ✓';
                e.target.classList.add('bg-green-500', 'hover:bg-green-600');
                e.target.classList.remove('bg-purple-600', 'hover:bg-purple-700');
                
                setTimeout(() => {
                    e.target.textContent = 'Ajouter';
                    e.target.classList.remove('bg-green-500', 'hover:bg-green-600');
                    e.target.classList.add('bg-purple-600', 'hover:bg-purple-700');
                }, 2000);
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'97afd528979dc79d',t:'MTc1NzE4MTI3Ny4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
