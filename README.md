<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>فايز شوب - متجر قطع الكمبيوتر</title>
    <style>
        /* التنسيق العام */
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        header {
            background: #35424a;
            color: #ffffff;
            padding: 20px 0;
            text-align: center;
        }

        nav ul {
            padding: 0;
            list-style: none;
        }

        nav ul li {
            display: inline;
            margin: 0 10px;
        }

        nav ul li a {
            color: #ffffff;
            text-decoration: none;
        }

        main {
            padding: 20px;
            margin-bottom: 60px; /* لمنع التداخل مع الفوتر */
        }

        footer {
            background: #35424a;
            color: #ffffff;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }

        /* تنسيق المنتجات */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px 0;
        }

        .product-card {
            background: #ffffff;
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 15px;
            text-align: center;
        }

        .product-card img {
            max-width: 100%;
            height: auto;
            border-bottom: 1px solid #ddd;
            margin-bottom: 15px;
        }

        .btn {
            display: inline-block;
            background: #35424a;
            color: #ffffff;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            margin-top: 10px;
        }

        /* تنسيق الفلاتر والبحث */
        .filter-section {
            display: flex;
            justify-content: space-between;
            margin: 20px 0;
            flex-wrap: wrap;
        }

        .filter {
            margin-bottom: 10px;
        }

        .filter select, .search-box input {
            padding: 8px;
            border-radius: 5px;
            border: 1px solid #ddd;
        }

        .search-box {
            margin-bottom: 10px;
        }

        /* تنسيق الفيديوهات */
        .video-container {
            margin: 20px 0;
        }

        .video-container iframe {
            width: 100%;
            height: 400px;
        }

        /* تنسيق صفحة الاتصال */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: #fff;
            padding: 20px;
            border-radius: 5px;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        /* إخفاء الصفحات غير النشطة */
        .page {
            display: none;
        }

        .active {
            display: block;
        }

        /* تنسيق صفحة البائع */
        .seller-info {
            background: #fff;
            padding: 20px;
            border-radius: 5px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
        }

        .seller-info h2 {
            color: #35424a;
            border-bottom: 2px solid #35424a;
            padding-bottom: 10px;
        }
    </style>
</head>
<body>
    <header>
        <h1>فايز شوب - متجر قطع الكمبيوتر</h1>
        <nav>
            <ul>
                <li><a href="#" onclick="showPage('home')">الرئيسية</a></li>
                <li><a href="#" onclick="showPage('products')">المنتجات</a></li>
                <li><a href="#" onclick="showPage('videos')">الفيديوهات</a></li>
                <li><a href="#" onclick="showPage('contact')">اتصل بنا</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- الصفحة الرئيسية -->
        <div id="home" class="page active">
            <section class="seller-info">
                <h2>معلومات عن البائع</h2>
                <p>مرحبًا بكم في فايز شوب، أنا فايز مقيم بولاية الجلفة، متخصص في بيع قطع الكمبيوتر:</p>
                <ul>
                    <li>كرت شاشة بجميع الأنواع</li>
                    <li>شاشات كمبيوتر</li>
                    <li>باور سبلاي</li>
                    <li>رامات بكل أنواعها (ما عدا القديم DDR2)</li>
                    <li>مذربوردات وكرت مار</li>
                    <li>كيسات كمبيوتر</li>
                    <li>أسلاك وملحقات</li>
                    <li>أساور تبريد</li>
                    <li>كيبوردات وماوس</li>
                    <li>معالجات</li>
                    <li>تجميعات كاملة</li>
                    <li>والكثير من قطع الكمبيوتر الأخرى</li>
                </ul>
                <p>نقدم منتجات عالية الجودة بأسعار تنافسية مع ضمان على جميع المنتجات.</p>
            </section>

            <section class="welcome">
                <h2>أهلاً بكم في فايز شوب</h2>
                <p>اكتشف أحدث منتجاتنا في عالم قطع الكمبيوتر</p>
                <a href="#" onclick="showPage('products')" class="btn">تصفح المنتجات</a>
            </section>

            <section class="featured-products">
                <h2>منتجات مميزة</h2>
                <div class="products-grid" id="featured-products">
                    <!-- سيتم إضافة المنتجات المميزة هنا عبر JavaScript -->
                </div>
            </section>
        </div>

        <!-- صفحة المنتجات -->
        <div id="products" class="page">
            <h2>منتجات فايز شوب</h2>
            
            <div class="filter-section">
                <div class="filter">
                    <select id="category-filter" onchange="filterProducts()">
                        <option value="all">جميع الفئات</option>
                        <option value="gpu">كروت الشاشة</option>
                        <option value="ram">الرامات</option>
                        <option value="motherboard">المذربورد/الكرت مار</option>
                        <option value="case">الكيس/البوكس</option>
                        <option value="cables">الأسلاك</option>
                        <option value="cooling">الأساور/التبريد</option>
                        <option value="keyboard">الكيبورد/ماوس</option>
                        <option value="monitor">الشاشات</option>
                        <option value="psu">الباور سبلاي</option>
                        <option value="cpu">المعالجات</option>
                        <option value="full-set">تجميعات كاملة</option>
                    </select>
                </div>
                
                <div class="search-box">
                    <input type="text" id="brand-search" placeholder="ابحث بالماركة..." onkeyup="searchByBrand()">
                </div>
            </div>
            
            <div class="products-grid" id="all-products">
                <!-- سيتم إضافة المنتجات هنا عبر JavaScript -->
            </div>
        </div>

        <!-- صفحة الفيديوهات -->
        <div id="videos" class="page">
            <h2>فيديوهات فايز شوب</h2>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/VIDEO_ID_1" frameborder="0" allowfullscreen></iframe>
                <p>فيديو تعريفي عن متجر فايز شوب</p>
            </div>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/VIDEO_ID_2" frameborder="0" allowfullscreen></iframe>
                <p>أحدث المنتجات المتوفرة</p>
            </div>
        </div>

        <!-- صفحة الاتصال -->
        <div id="contact" class="page">
            <h2>اتصل بفايز شوب</h2>
            <div class="contact-form">
                <form>
                    <input type="text" placeholder="اسمك" required>
                    <input type="email" placeholder="بريدك الإلكتروني" required>
                    <input type="tel" placeholder="رقم هاتفك">
                    <textarea placeholder="رسالتك" rows="5" required></textarea>
                    <button type="submit" class="btn">إرسال</button>
                </form>
            </div>
        </div>
    </main>

    <footer>
        <p>&copy; 2023 فايز شوب - متجر قطع الكمبيوتر. جميع الحقوق محفوظة.</p>
    </footer>

    <script>
        // بيانات المنتجات
        const products = [
            {
                id: 1,
                name: "كرت شاشة NVIDIA RTX 3080",
                price: 1200,
                category: "gpu",
                brand: "NVIDIA",
                image: "https://via.placeholder.com/300x200?text=RTX+3080",
                description: "كرت شاشة قوي للألعاب والتطبيقات الاحترافية",
                featured: true
            },
            {
                id: 2,
                name: "شاشة سامسونج 27 بوصة",
                price: 350,
                category: "monitor",
                brand: "Samsung",
                image: "https://via.placeholder.com/300x200?text=Monitor+27",
                description: "شاشة بدقة 4K مع تقنية HDR",
                featured: true
            },
            {
                id: 3,
                name: "رام DDR4 16GB",
                price: 80,
                category: "ram",
                brand: "Corsair",
                image: "https://via.placeholder.com/300x200?text=DDR4+16GB",
                description: "رامات بسرعة 3200MHz",
                featured: true
            },
            {
                id: 4,
                name: "باور سبلاي 750W",
                price: 120,
                category: "psu",
                brand: "Cooler Master",
                image: "https://via.placeholder.com/300x200?text=PSU+750W",
                description: "باور سبلاي ذهبي كفاءة عالية",
                featured: false
            },
            {
                id: 5,
                name: "كرت شاشة AMD RX 6800",
                price: 900,
                category: "gpu",
                brand: "AMD",
                image: "https://via.placeholder.com/300x200?text=RX+6800",
                description: "أداء عالي في الألعاب",
                featured: false
            },
            {
                id: 6,
                name: "رام DDR4 32GB",
                price: 150,
                category: "ram",
                brand: "Kingston",
                image: "https://via.placeholder.com/300x200?text=DDR4+32GB",
                description: "رامات بسرعة 3600MHz",
                featured: false
            },
            {
                id: 7,
                name: "مذربورد ASUS ROG",
                price: 250,
                category: "motherboard",
                brand: "ASUS",
                image: "https://via.placeholder.com/300x200?text=ASUS+ROG",
                description: "لوحة أم للألعاب مع منافذ متعددة",
                featured: false
            },
            {
                id: 8,
                name: "كيس كمبيوتر",
                price: 70,
                category: "case",
                brand: "Deepcool",
                image: "https://via.placeholder.com/300x200?text=PC+Case",
                description: "كيس كمبيوتر مع زجاج جانبي",
                featured: false
            },
            {
                id: 9,
                name: "أساور تبريد",
                price: 40,
                category: "cooling",
                brand: "Thermaltake",
                image: "https://via.placeholder.com/300x200?text=Cooling+Fans",
                description: "مجموعة أساور تبريد RGB",
                featured: false
            },
            {
                id: 10,
                name: "معالج Intel i7",
                price: 350,
                category: "cpu",
                brand: "Intel",
                image: "https://via.placeholder.com/300x200?text=Intel+i7",
                description: "معالج قوي للألعاب والتطبيقات",
                featured: false
            }
        ];

        // عرض الصفحة المطلوبة
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');
            
            if (pageId === 'products') {
                displayAllProducts();
            } else if (pageId === 'home') {
                displayFeaturedProducts();
            }
        }

        // عرض المنتجات المميزة
        function displayFeaturedProducts() {
            const featuredContainer = document.getElementById('featured-products');
            featuredContainer.innerHTML = '';
            
            const featuredProducts = products.filter(product => product.featured);
            
            featuredProducts.forEach(product => {
                featuredContainer.innerHTML += `
                    <div class="product-card">
                        <img src="${product.image}" alt="${product.name}">
                        <h3>${product.name}</h3>
                        <p>${product.description}</p>
                        <p><strong>السعر: $${product.price}</strong></p>
                        <a href="#" class="btn">تفاصيل</a>
                    </div>
                `;
            });
        }

        // عرض جميع المنتجات
        function displayAllProducts() {
            const productsContainer = document.getElementById('all-products');
            productsContainer.innerHTML = '';
            
            products.forEach(product => {
                productsContainer.innerHTML += `
                    <div class="product-card" data-category="${product.category}" data-brand="${product.brand.toLowerCase()}">
                        <img src="${product.image}" alt="${product.name}">
                        <h3>${product.name}</h3>
                        <p>${product.description}</p>
                        <p><strong>السعر: $${product.price}</strong></p>
                        <a href="#" class="btn">تفاصيل</a>
                    </div>
                `;
            });
        }

        // تصفية المنتجات حسب الفئة
        function filterProducts() {
            const category = document.getElementById('category-filter').value;
            const searchTerm = document.getElementById('brand-search').value.toLowerCase();
            const productCards = document.querySelectorAll('.product-card');
            
            productCards.forEach(card => {
                const cardCategory = card.getAttribute('data-category');
                const cardBrand = card.getAttribute('data-brand');
                
                const categoryMatch = category === 'all' || cardCategory === category;
                const brandMatch = cardBrand.includes(searchTerm);
                
                if (categoryMatch && brandMatch) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // البحث حسب الماركة
        function searchByBrand() {
            filterProducts();
        }

        // تهيئة الصفحة عند التحميل
        window.onload = function() {
            displayFeaturedProducts();
        };
    </script>
</body>
</html>
