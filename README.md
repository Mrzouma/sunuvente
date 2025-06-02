<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SunuVente - Des textes qui vendent. Des ventes qui décollent.</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Custom colors inspired by Senegal flag */
        :root {
            --color-yellow: #FCD116; /* Jaune */
            --color-green: #00843D; /* Vert */
            --color-red: #EF3340;   /* Rouge */
            --color-black: #000000; /* Noir */
        }


        /* Custom Tailwind configuration */
        .bg-sunu-yellow { background-color: var(--color-yellow); }
        .text-sunu-yellow { color: var(--color-yellow); }
        .bg-sunu-green { background-color: var(--color-green); }
        .text-sunu-green { color: var(--color-green); }
        .bg-sunu-red { background-color: var(--color-red); }
        .text-sunu-red { color: var(--color-red); }
        .bg-sunu-black { background-color: var(--color-black); }
        .text-sunu-black { color: var(--color-black); }


        /* Font Inter */
        body {
            font-family: 'Inter', sans-serif;
        }


        /* Smooth page transition */
        .page-transition {
            transition: opacity 0.5s ease-in-out;
        }


        /* Loading spinner */
        .spinner {
            border: 4px solid rgba(255, 255, 255, 0.3);
            border-top: 4px solid var(--color-green);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
        }


        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }


        /* Custom modal for alerts */
        .modal {
            display: none; /* Hidden by default */
            position: fixed; /* Stay in place */
            z-index: 1000; /* Sit on top */
            left: 0;
            top: 0;
            width: 100%; /* Full width */
            height: 100%; /* Full height */
            overflow: auto; /* Enable scroll if needed */
            background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
            justify-content: center;
            align-items: center;
        }


        .modal-content {
            background-color: #fefefe;
            margin: auto;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 80%;
            max-width: 400px;
            text-align: center;
        }


        .close-button {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }


        .close-button:hover,
        .close-button:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">


    <div id="customModal" class="modal">
        <div class="modal-content">
            <span class="close-button" onclick="document.getElementById('customModal').style.display='none'">&times;</span>
            <p id="modalMessage" class="text-lg font-semibold"></p>
            <button class="mt-4 px-4 py-2 bg-sunu-green text-white rounded-md hover:bg-green-700 transition-colors" onclick="document.getElementById('customModal').style.display='none'">OK</button>
        </div>
    </div>


    <div id="homePage" class="min-h-screen flex flex-col page-transition">
        <header class="bg-sunu-green text-white p-6 shadow-md rounded-b-lg">
            <div class="container mx-auto flex flex-col md:flex-row justify-between items-center">
                <h1 class="text-4xl font-bold mb-2 md:mb-0">SunuVente</h1>
                <p class="text-xl italic">Des textes qui vendent. Des ventes qui décollent.</p>
            </div>
        </header>


        <main class="flex-grow container mx-auto px-4 py-8 flex flex-col items-center justify-center">
            <div class="flex flex-col md:flex-row items-center justify-center gap-8 mb-12">
                <div class="text-center md:text-left max-w-lg">
                    <h2 class="text-3xl md:text-4xl font-extrabold text-sunu-black mb-4 leading-tight">
                        Transformez vos produits en histoires qui captivent et convertissent.
                    </h2>
                    <p class="text-lg text-gray-600 mb-6">
                        Générez des descriptions de produits et des hashtags optimisés en quelques clics.
                    </p>
                    <button id="generateTextHomeBtn" class="bg-sunu-red text-white font-bold py-3 px-8 rounded-full shadow-lg hover:bg-red-700 transition-transform transform hover:scale-105 focus:outline-none focus:ring-4 focus:ring-red-300">
                        Générer mon texte de vente
                    </button>
                </div>
                <div class="w-full md:w-1/2 flex justify-center">
                    <img src="https://placehold.co/500x350/00843D/FFFFFF?text=Entrepreneur+Africain" alt="Entrepreneur africain souriant avec téléphone ou ordinateur" class="rounded-lg shadow-xl max-w-full h-auto">
                </div>
            </div>


            <section class="w-full bg-white p-8 rounded-lg shadow-md mb-12">
                <h3 class="text-3xl font-bold text-center text-sunu-black mb-8">Pourquoi utiliser SunuVente ?</h3>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                    <div class="flex flex-col items-center text-center p-4 rounded-lg bg-gray-50 hover:shadow-lg transition-shadow">
                        <i class="fas fa-robot text-5xl text-sunu-green mb-4"></i>
                        <h4 class="text-xl font-semibold text-sunu-black mb-2">Création de textes IA</h4>
                        <p class="text-gray-600">Des descriptions uniques et percutantes générées par intelligence artificielle.</p>
                    </div>
                    <div class="flex flex-col items-center text-center p-4 rounded-lg bg-gray-50 hover:shadow-lg transition-shadow">
                        <i class="fas fa-share-alt text-5xl text-sunu-red mb-4"></i>
                        <h4 class="text-xl font-semibold text-sunu-black mb-2">Optimisation selon la plateforme</h4>
                        <p class="text-gray-600">Textes adaptés à Facebook, Instagram, TikTok et plus encore.</p>
                    </div>
                    <div class="flex flex-col items-center text-center p-4 rounded-lg bg-gray-50 hover:shadow-lg transition-shadow">
                        <i class="fas fa-phone-alt text-5xl text-sunu-yellow mb-4"></i>
                        <h4 class="text-xl font-semibold text-sunu-black mb-2">Insertion automatique du numéro</h4>
                        <p class="text-gray-600">Votre contact intégré fluidement pour des commandes directes.</p>
                    </div>
                    <div class="flex flex-col items-center text-center p-4 rounded-lg bg-gray-50 hover:shadow-lg transition-shadow">
                        <i class="fas fa-hashtag text-5xl text-sunu-black mb-4"></i>
                        <h4 class="text-xl font-semibold text-sunu-black mb-2">Génération de hashtags puissants</h4>
                        <p class="text-gray-600">Atteignez une audience plus large avec des hashtags pertinents.</p>
                    </div>
                </div>
            </section>


            <section class="w-full bg-sunu-yellow p-8 rounded-lg shadow-md text-center">
                <h3 class="text-3xl font-bold text-sunu-black mb-6">Prêt à booster vos ventes ?</h3>
                <button id="generateTextCtaBtn" class="bg-sunu-green text-white font-bold py-4 px-10 rounded-full shadow-lg hover:bg-green-700 transition-transform transform hover:scale-105 focus:outline-none focus:ring-4 focus:ring-green-300">
                    Générer mon texte de vente maintenant
                </button>
            </section>
        </main>


        <a href="https://wa.me/221787196900" target="_blank" class="fixed bottom-8 right-8 bg-green-500 text-white p-4 rounded-full shadow-lg hover:bg-green-600 transition-colors z-50">
            <i class="fab fa-whatsapp text-3xl"></i>
        </a>


        <footer class="bg-sunu-black text-white p-6 text-center mt-8 rounded-t-lg">
            <p class="text-sm">&copy; 2025 SunuVente – Développé par Mr. Zouma | 📞 78 719 69 00</p>
        </footer>
    </div>


    <div id="formPage" class="min-h-screen flex flex-col page-transition hidden opacity-0">
        <header class="bg-sunu-green text-white p-6 shadow-md rounded-b-lg flex justify-between items-center">
            <button id="backToHomeBtn" class="text-white text-xl hover:text-gray-200 transition-colors focus:outline-none">
                <i class="fas fa-arrow-left mr-2"></i> Retour
            </button>
            <h1 class="text-3xl font-bold">Générer votre texte de vente</h1>
            <div></div> </header>


        <main class="flex-grow container mx-auto px-4 py-8">
            <div class="bg-white p-8 rounded-lg shadow-md max-w-2xl mx-auto">
                <h2 class="text-2xl font-bold text-sunu-black mb-6 text-center">Dites-nous en plus sur votre produit</h2>
                <form id="salesForm" class="space-y-6">
                    <div>
                        <label for="productName" class="block text-sm font-medium text-gray-700">Nom du produit <span class="text-red-500">*</span></label>
                        <input type="text" id="productName" name="productName" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-sunu-green focus:border-sunu-green">
                    </div>
                    <div>
                        <label for="description" class="block text-sm font-medium text-gray-700">Description / Fonction principale <span class="text-red-500">*</span></label>
                        <textarea id="description" name="description" rows="3" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-sunu-green focus:border-sunu-green"></textarea>
                    </div>
                    <div>
                        <label for="utility" class="block text-sm font-medium text-gray-700">Utilité du produit <span class="text-red-500">*</span></label>
                        <textarea id="utility" name="utility" rows="3" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-sunu-green focus:border-sunu-green"></textarea>
                    </div>
                    <div>
                        <label for="target" class="block text-sm font-medium text-gray-700">Cible (ex. : femmes, jeunes, sportifs...) <span class="text-red-500">*</span></label>
                        <input type="text" id="target" name="target" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-sunu-green focus:border-sunu-green">
                    </div>
                    <div>
                        <label for="tone" class="block text-sm font-medium text-gray-700">Ton du texte de vente <span class="text-red-500">*</span></label>
                        <select id="tone" name="tone" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-sunu-green focus:border-sunu-green">
                            <option value="professionnel">Professionnel</option>
                            <option value="humoristique">Humoristique</option>
                            <option value="convainquant">Convainquant</option>
                            <option value="chaleureux">Chaleureux</option>
                            <option value="dynamique">Dynamique</option>
                        </select>
                    </div>
                    <div>
                        <label for="socialMedia" class="block text-sm font-medium text-gray-700">Réseau social ciblé <span class="text-red-500">*</span></label>
                        <select id="socialMedia" name="socialMedia" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-sunu-green focus:border-sunu-green">
                            <option value="Facebook">Facebook</option>
                            <option value="Instagram">Instagram</option>
                            <option value="TikTok">TikTok</option>
                            <option value="LinkedIn">LinkedIn</option>
                            <option value="X (Twitter)">X (Twitter)</option>
                        </select>
                    </div>
                    <div>
                        <label for="phoneNumber" class="block text-sm font-medium text-gray-700">Numéro de téléphone (facultatif)</label>
                        <input type="tel" id="phoneNumber" name="phoneNumber" pattern="[0-9]{9}" placeholder="Ex: 771234567" class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-sunu-green focus:border-sunu-green">
                        <p class="mt-1 text-sm text-gray-500">Format: 9 chiffres (ex: 771234567)</p>
                    </div>
                    <button type="submit" class="w-full bg-sunu-green text-white font-bold py-3 px-4 rounded-md shadow-lg hover:bg-green-700 transition-colors focus:outline-none focus:ring-4 focus:ring-green-300">
                        <span id="generateBtnText">Générer le texte de vente</span>
                        <div id="loadingSpinner" class="spinner mx-auto hidden"></div>
                    </button>
                </form>


                <div id="resultsSection" class="mt-8 p-6 bg-gray-50 rounded-lg shadow-inner hidden">
                    <h3 class="text-xl font-bold text-sunu-black mb-4">Votre texte de vente généré :</h3>
                    <div class="bg-white p-4 rounded-md border border-gray-200 mb-4">
                        <p id="generatedText" class="whitespace-pre-wrap text-gray-800"></p>
                    </div>
                    <button id="copyTextBtn" class="w-full bg-sunu-yellow text-sunu-black font-bold py-2 px-4 rounded-md shadow hover:bg-yellow-400 transition-colors focus:outline-none focus:ring-4 focus:ring-yellow-300 mb-4">
                        Copier le texte
                    </button>


                    <h3 class="text-xl font-bold text-sunu-black mb-4">Hashtags pertinents :</h3>
                    <div class="bg-white p-4 rounded-md border border-gray-200 mb-4">
                        <p id="generatedHashtags" class="whitespace-pre-wrap text-gray-800"></p>
                    </div>
                    <button id="copyHashtagsBtn" class="w-full bg-sunu-yellow text-sunu-black font-bold py-2 px-4 rounded-md shadow hover:bg-yellow-400 transition-colors focus:outline-none focus:ring-4 focus:ring-yellow-300">
                        Copier les hashtags
                    </button>
                </div>
            </div>
        </main>
    </div>


    <script>
        // Function to show custom modal messages
        function showCustomModal(message) {
            document.getElementById('modalMessage').innerText = message;
            document.getElementById('customModal').style.display = 'flex';
        }


        // Get elements
        const homePage = document.getElementById('homePage');
        const formPage = document.getElementById('formPage');
        const generateTextHomeBtn = document.getElementById('generateTextHomeBtn');
        const generateTextCtaBtn = document.getElementById('generateTextCtaBtn');
        const backToHomeBtn = document.getElementById('backToHomeBtn');
        const salesForm = document.getElementById('salesForm');
        const loadingSpinner = document.getElementById('loadingSpinner');
        const generateBtnText = document.getElementById('generateBtnText');
        const resultsSection = document.getElementById('resultsSection');
        const generatedText = document.getElementById('generatedText');
        const generatedHashtags = document.getElementById('generatedHashtags');
        const copyTextBtn = document.getElementById('copyTextBtn');
        const copyHashtagsBtn = document.getElementById('copyHashtagsBtn');


        // Function to navigate between pages with a fade effect
        function navigateTo(pageToShow, pageToHide) {
            pageToHide.classList.add('opacity-0');
            setTimeout(() => {
                pageToHide.classList.add('hidden');
                pageToShow.classList.remove('hidden');
                setTimeout(() => {
                    pageToShow.classList.remove('opacity-0');
                }, 10); // Small delay to trigger transition
            }, 500); // Duration of the fade-out transition
        }


        // Event listeners for page navigation
        generateTextHomeBtn.addEventListener('click', () => navigateTo(formPage, homePage));
        generateTextCtaBtn.addEventListener('click', () => navigateTo(formPage, homePage));
        backToHomeBtn.addEventListener('click', () => {
            navigateTo(homePage, formPage);
            // Reset form and hide results when going back to home
            salesForm.reset();
            resultsSection.classList.add('hidden');
        });


        // Handle form submission
        salesForm.addEventListener('submit', async (e) => {
            e.preventDefault();


            // Show loading spinner and disable button
            generateBtnText.classList.add('hidden');
            loadingSpinner.classList.remove('hidden');
            salesForm.querySelector('button[type="submit"]').disabled = true;
            resultsSection.classList.add('hidden'); // Hide previous results


            const formData = new FormData(salesForm);
            const productName = formData.get('productName');
            const description = formData.get('description');
            const utility = formData.get('utility');
            const target = formData.get('target');
            const tone = formData.get('tone');
            const socialMedia = formData.get('socialMedia');
            const phoneNumber = formData.get('phoneNumber') || 'Non fourni'; // Optional field


            // Construct the prompt for the LLM
            // Updated prompt to include target audience and social media platform in the sales text
            const prompt = `Génère un texte de vente percutant et 5-10 hashtags pertinents pour un produit avec les détails suivants. Le texte doit être en français, adapté au réseau social ciblé (${socialMedia}) et au ton choisi (${tone}). Intègre le fait que ce texte est spécifiquement ciblé pour ${target}. Si un numéro de téléphone est fourni, intègre-le naturellement dans le texte. Utilise parfois des emojis pertinents comme 🚀, 💥, 📦, 💬, ✅, ✨, 🔥, 💡, 🌟.


            Format de sortie JSON:
            {
              "salesText": "[texte de vente généré]",
              "hashtags": ["#hashtag1", "#hashtag2", "..."]
            }


            Détails du produit:
            Nom du produit: ${productName}
            Description / Fonction principale: ${description}
            Utilité du produit: ${utility}
            Cible: ${target}
            Ton: ${tone}
            Réseau social ciblé: ${socialMedia}
            Numéro de téléphone: ${phoneNumber}`;


            try {
                let chatHistory = [];
                chatHistory.push({ role: "user", parts: [{ text: prompt }] });


                const payload = {
                    contents: chatHistory,
                    generationConfig: {
                        responseMimeType: "application/json",
                        responseSchema: {
                            type: "OBJECT",
                            properties: {
                                "salesText": { "type": "STRING" },
                                "hashtags": {
                                    "type": "ARRAY",
                                    "items": { "type": "STRING" }
                                }
                            },
                            "propertyOrdering": ["salesText", "hashtags"]
                        }
                    }
                };


                const apiKey = "curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=GEMINI_API_KEY" \
  -H 'Content-Type: application/json' \
  -X POST \
  -d '{
    "contents": [
      {
        "parts": [
          {
            "text": "Explain how AI works in a few words"
          }
        ]
      }
    ]
  }'"; // Canvas will automatically provide the API key
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;


                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });


                const result = await response.json();


                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    const jsonString = result.candidates[0].content.parts[0].text;
                    const parsedJson = JSON.parse(jsonString);


                    generatedText.innerText = parsedJson.salesText;
                    generatedHashtags.innerText = parsedJson.hashtags.join(' ');
                    resultsSection.classList.remove('hidden');
                } else {
                    showCustomModal("Désolé, je n'ai pas pu générer le texte de vente. Veuillez réessayer.");
                    console.error("Unexpected API response structure:", result);
                }


            } catch (error) {
                showCustomModal("Une erreur est survenue lors de la génération du texte. Veuillez vérifier votre connexion ou réessayer plus tard.");
                console.error("Error generating sales text:", error);
            } finally {
                // Hide loading spinner and enable button
                loadingSpinner.classList.add('hidden');
                generateBtnText.classList.remove('hidden');
                salesForm.querySelector('button[type="submit"]').disabled = false;
            }
        });


        // Copy text to clipboard
        copyTextBtn.addEventListener('click', () => {
            const textToCopy = generatedText.innerText;
            try {
                const textarea = document.createElement('textarea');
                textarea.value = textToCopy;
                document.body.appendChild(textarea);
                textarea.select();
                document.execCommand('copy');
                document.body.removeChild(textarea);
                showCustomModal("Texte copié !");
            } catch (err) {
                showCustomModal("Échec de la copie du texte.");
                console.error('Failed to copy text: ', err);
            }
        });


        // Copy hashtags to clipboard
        copyHashtagsBtn.addEventListener('click', () => {
            const hashtagsToCopy = generatedHashtags.innerText;
            try {
                const textarea = document.createElement('textarea');
                textarea.value = hashtagsToCopy;
                document.body.appendChild(textarea);
                textarea.select();
                document.execCommand('copy');
                document.body.removeChild(textarea);
                showCustomModal("Hashtags copiés !");
            } catch (err) {
                showCustomModal("Échec de la copie des hashtags.");
                console.error('Failed to copy hashtags: ', err);
            }
        });
    </script>
</body>
</html>
