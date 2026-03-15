# Task-Flow
Official website for TaskFlow – a platform to connect freelancers and clients.
    html { scroll-behavior: smooth; }
    
    @keyframes float {
        0%, 100% { transform: translateY(0px); }
        50% { transform: translateY(-10px); }
    }
    
    @keyframes pulse-glow {
        0%, 100% { box-shadow: 0 0 20px rgba(59, 130, 246, 0.3); }
        50% { box-shadow: 0 0 40px rgba(59, 130, 246, 0.6); }
    }
    
    .animate-float { animation: float 3s ease-in-out infinite; }
    .animate-pulse-glow { animation: pulse-glow 2s ease-in-out infinite; }
    
    .text-gradient {
        background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 50%, #06b6d4 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
    
    .glass {
        background: rgba(255, 255, 255, 0.7);
        backdrop-filter: blur(10px);
        border: 1px solid rgba(255, 255, 255, 0.2);
    }
    
    .glass-dark {
        background: rgba(30, 58, 138, 0.9);
        backdrop-filter: blur(10px);
    }
    
    .hover-lift {
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .hover-lift:hover {
        transform: translateY(-5px);
        box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
    }
    
    ::-webkit-scrollbar { width: 8px; }
    ::-webkit-scrollbar-track { background: #f1f5f9; }
    ::-webkit-scrollbar-thumb { background: #3b82f6; border-radius: 4px; }
    ::-webkit-scrollbar-thumb:hover { background: #1e40af; }
    
    .bg-pattern {
        background-image: radial-gradient(circle at 1px 1px, rgba(59, 130, 246, 0.15) 1px, transparent 0);
        background-size: 40px 40px;
    }
    
    /* Modal Animation */
    .modal-enter {
        opacity: 0;
        transform: scale(0.95);
    }
    .modal-enter-active {
        opacity: 1;
        transform: scale(1);
        transition: opacity 0.3s ease, transform 0.3s ease;
    }
    .modal-exit {
        opacity: 1;
        transform: scale(1);
    }
    .modal-exit-active {
        opacity: 0;
        transform: scale(0.95);
        transition: opacity 0.2s ease, transform 0.2s ease;
    }
    
    /* Job Card Badge Colors */
    .badge-remote { @apply bg-green-100 text-green-800; }
    .badge-hybrid { @apply bg-blue-100 text-blue-800; }
    .badge-onsite { @apply bg-orange-100 text-orange-800; }
    .badge-urgent { @apply bg-red-100 text-red-800; }
    .badge-featured { @apply bg-purple-100 text-purple-800; }
</style>

<!-- Navigation -->
<nav class="fixed w-full z-50 glass border-b border-slate-200/50 transition-all duration-300" id="navbar">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-20">
            <div class="flex-shrink-0 flex items-center gap-2 cursor-pointer" onclick="window.scrollTo(0,0)">
                <div class="w-10 h-10 bg-gradient-to-br from-blue-900 to-blue-600 rounded-lg flex items-center justify-center">
                    <i data-lucide="hexagon" class="w-6 h-6 text-white"></i>
                </div>
                <span class="text-2xl font-bold text-slate-900 tracking-tight">Task<span class="text-blue-600">Flow</span></span>
            </div>

            <div class="hidden md:flex items-center space-x-8">
                <a href="#jobs" class="text-slate-600 hover:text-blue-900 font-medium transition-colors">Browse Jobs</a>
                <a href="#categories" class="text-slate-600 hover:text-blue-900 font-medium transition-colors">Categories</a>
                <a href="#how-it-works" class="text-slate-600 hover:text-blue-900 font-medium transition-colors">How it Works</a>
                <a href="#companies" class="text-slate-600 hover:text-blue-900 font-medium transition-colors">Companies</a>
            </div>

            <div class="hidden md:flex items-center space-x-4">
                <button class="text-slate-700 hover:text-blue-900 font-medium px-4 py-2 transition-colors">Sign In</button>
                <button class="bg-blue-900 hover:bg-blue-800 text-white px-6 py-2.5 rounded-full font-medium transition-all hover:shadow-lg hover:shadow-blue-900/30">
                    Upload Resume
                </button>
            </div>

            <div class="md:hidden flex items-center">
                <button onclick="toggleMobileMenu()" class="text-slate-700 hover:text-blue-900 p-2">
                    <i data-lucide="menu" class="w-6 h-6" id="menu-icon"></i>
                </button>
            </div>
        </div>
    </div>

    <div id="mobile-menu" class="hidden md:hidden glass border-t border-slate-200">
        <div class="px-4 pt-2 pb-6 space-y-2">
            <a href="#jobs" class="block px-3 py-2 text-slate-700 hover:text-blue-900 font-medium">Browse Jobs</a>
            <a href="#categories" class="block px-3 py-2 text-slate-700 hover:text-blue-900 font-medium">Categories</a>
            <a href="#how-it-works" class="block px-3 py-2 text-slate-700 hover:text-blue-900 font-medium">How it Works</a>
            <a href="#companies" class="block px-3 py-2 text-slate-700 hover:text-blue-900 font-medium">Companies</a>
            <div class="pt-4 space-y-2">
                <button class="w-full text-center text-slate-700 font-medium py-2 border border-slate-300 rounded-lg">Sign In</button>
                <button class="w-full bg-blue-900 text-white font-medium py-2 rounded-lg">Upload Resume</button>
            </div>
        </div>
    </div>
</nav>

<!-- Hero Section -->
<section class="relative pt-32 pb-20 lg:pt-40 lg:pb-32 overflow-hidden bg-pattern">
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
        <div class="absolute -top-40 -right-40 w-96 h-96 bg-blue-400/20 rounded-full blur-3xl"></div>
        <div class="absolute top-1/2 -left-20 w-72 h-72 bg-cyan-400/20 rounded-full blur-3xl"></div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative">
        <div class="grid lg:grid-cols-2 gap-12 items-center">
            <div class="space-y-8">
                <div class="inline-flex items-center gap-2 px-4 py-2 bg-blue-50 border border-blue-100 rounded-full text-blue-800 text-sm font-medium">
                    <span class="w-2 h-2 bg-blue-600 rounded-full animate-pulse"></span>
                    2,500+ New Jobs Added This Week
                </div>
                
                <h1 class="text-5xl lg:text-7xl font-bold leading-tight text-slate-900">
                    Find Your Next <br>
                    <span class="text-gradient">Freelance Gig</span><br>
                    Today
                </h1>
                
                <p class="text-xl text-slate-600 max-w-lg leading-relaxed">
                    Connect with top-tier companies hiring elite freelancers. High-paying remote opportunities in tech, design, AI, and digital transformation.
                </p>

                <!-- Job Search Box -->
                <div class="bg-white p-2 rounded-2xl shadow-xl shadow-slate-200/50 border border-slate-100 max-w-2xl">
                    <div class="flex flex-col sm:flex-row gap-2">
                        <div class="flex-1 relative">
                            <i data-lucide="search" class="absolute left-4 top-1/2 -translate-y-1/2 w-5 h-5 text-slate-400"></i>
                            <input type="text" id="jobSearch" placeholder="Job title, keywords, or company" 
                                class="w-full pl-12 pr-4 py-4 rounded-xl bg-slate-50 border-0 focus:ring-2 focus:ring-blue-500 text-slate-700 placeholder-slate-400">
                        </div>
                        <div class="flex-1 relative hidden sm:block">
                            <i data-lucide="map-pin" class="absolute left-4 top-1/2 -translate-y-1/2 w-5 h-5 text-slate-400"></i>
                            <select class="w-full pl-12 pr-4 py-4 rounded-xl bg-slate-50 border-0 focus:ring-2 focus:ring-blue-500 text-slate-700 appearance-none cursor-pointer">
                                <option>All Locations</option>
                                <option>Remote</option>
                                <option>United States</option>
                                <option>Europe</option>
                                <option>Asia Pacific</option>
                            </select>
                        </div>
                        <button onclick="scrollToJobs()" class="bg-blue-900 hover:bg-blue-800 text-white px-8 py-4 rounded-xl font-semibold transition-all hover:shadow-lg hover:shadow-blue-900/30 flex items-center justify-center gap-2">
                            Find Jobs
                            <i data-lucide="arrow-right" class="w-5 h-5"></i>
                        </button>
                    </div>
                </div>

                <div class="flex items-center gap-8 pt-4">
                    <div>
                        <div class="text-3xl font-bold text-slate-900">15k+</div>
                        <div class="text-sm text-slate-500">Active Jobs</div>
                    </div>
                    <div class="w-px h-12 bg-slate-200"></div>
                    <div>
                        <div class="text-3xl font-bold text-slate-900">$85/hr</div>
                        <div class="text-sm text-slate-500">Avg. Rate</div>
                    </div>
                    <div class="w-px h-12 bg-slate-200"></div>
                    <div>
                        <div class="text-3xl font-bold text-slate-900">48h</div>
                        <div class="text-sm text-slate-500">Avg. Hire Time</div>
                    </div>
                </div>
            </div>

            <div class="relative lg:h-[600px] flex items-center justify-center">
                <!-- Job Card Preview -->
                <div class="relative z-10 bg-white rounded-3xl shadow-2xl shadow-blue-900/10 p-6 w-full max-w-md animate-float">
                    <div class="flex items-center justify-between mb-6">
                        <div class="flex items-center gap-3">
                            <div class="w-12 h-12 bg-blue-100 rounded-xl flex items-center justify-center">
                                <i data-lucide="briefcase" class="w-6 h-6 text-blue-600"></i>
                            </div>
                            <div>
                                <div class="font-semibold text-slate-900">Senior React Developer</div>
                                <div class="text-sm text-slate-500">TechCorp Inc.</div>
                            </div>
                        </div>
                        <span class="px-3 py-1 bg-green-100 text-green-700 rounded-full text-xs font-semibold">New</span>
                    </div>
                    
                    <div class="space-y-3 mb-6">
                        <div class="flex items-center gap-2 text-slate-600">
                            <i data-lucide="dollar-sign" class="w-4 h-4"></i>
                            <span class="font-semibold text-slate-900">$120 - $150/hr</span>
                        </div>
                        <div class="flex items-center gap-2 text-slate-600">
                            <i data-lucide="map-pin" class="w-4 h-4"></i>
                            <span>Remote • Worldwide</span>
                        </div>
                        <div class="flex items-center gap-2 text-slate-600">
                            <i data-lucide="clock" class="w-4 h-4"></i>
                            <span>Posted 2 hours ago</span>
                        </div>
                    </div>

                    <div class="flex flex-wrap gap-2 mb-6">
                        <span class="px-3 py-1 bg-slate-100 text-slate-700 rounded-lg text-xs font-medium">React</span>
                        <span class="px-3 py-1 bg-slate-100 text-slate-700 rounded-lg text-xs font-medium">TypeScript</span>
                        <span class="px-3 py-1 bg-slate-100 text-slate-700 rounded-lg text-xs font-medium">Node.js</span>
                    </div>

                    <button class="w-full bg-blue-900 text-white py-3 rounded-xl font-semibold hover:bg-blue-800 transition-colors">
                        Apply Now
                    </button>
                </div>

                <!-- Floating Stats -->
                <div class="absolute -top-4 -right-4 bg-white rounded-2xl shadow-xl p-4 animate-float" style="animation-delay: 0.5s;">
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 bg-green-100 rounded-full flex items-center justify-center">
                            <i data-lucide="trending-up" class="w-6 h-6 text-green-600"></i>
                        </div>
                        <div>
                            <div class="text-sm font-semibold text-slate-900">+24% Job Growth</div>
                            <div class="text-xs text-slate-500">This month</div>
                        </div>
                    </div>
                </div>

                <div class="absolute -bottom-4 -left-4 bg-white rounded-2xl shadow-xl p-4 animate-float" style="animation-delay: 1s;">
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 bg-blue-100 rounded-full flex items-center justify-center">
                            <i data-lucide="users" class="w-6 h-6 text-blue-600"></i>
                        </div>
                        <div>
                            <div class="text-sm font-semibold text-slate-900">500+ Companies</div>
                            <div class="text-xs text-slate-500">Hiring now</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Job Categories -->
<section id="categories" class="py-16 bg-white border-y border-slate-100">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-8 gap-4">
            <button onclick="filterJobs('all')" class="category-btn active p-4 rounded-2xl border-2 border-blue-900 bg-blue-900 text-white text-center transition-all hover:shadow-lg">
                <i data-lucide="layout-grid" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">All Jobs</span>
            </button>
            <button onclick="filterJobs('development')" class="category-btn p-4 rounded-2xl border-2 border-slate-200 hover:border-blue-500 text-slate-700 text-center transition-all hover:shadow-lg">
                <i data-lucide="code-2" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">Development</span>
            </button>
            <button onclick="filterJobs('design')" class="category-btn p-4 rounded-2xl border-2 border-slate-200 hover:border-purple-500 text-slate-700 text-center transition-all hover:shadow-lg">
                <i data-lucide="palette" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">Design</span>
            </button>
            <button onclick="filterJobs('ai')" class="category-btn p-4 rounded-2xl border-2 border-slate-200 hover:border-cyan-500 text-slate-700 text-center transition-all hover:shadow-lg">
                <i data-lucide="brain" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">AI/ML</span>
            </button>
            <button onclick="filterJobs('marketing')" class="category-btn p-4 rounded-2xl border-2 border-slate-200 hover:border-amber-500 text-slate-700 text-center transition-all hover:shadow-lg">
                <i data-lucide="megaphone" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">Marketing</span>
            </button>
            <button onclick="filterJobs('writing')" class="category-btn p-4 rounded-2xl border-2 border-slate-200 hover:border-rose-500 text-slate-700 text-center transition-all hover:shadow-lg">
                <i data-lucide="pen-tool" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">Writing</span>
            </button>
            <button onclick="filterJobs('admin')" class="category-btn p-4 rounded-2xl border-2 border-slate-200 hover:border-green-500 text-slate-700 text-center transition-all hover:shadow-lg">
                <i data-lucide="clipboard-list" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">Admin</span>
            </button>
            <button onclick="filterJobs('customer')" class="category-btn p-4 rounded-2xl border-2 border-slate-200 hover:border-indigo-500 text-slate-700 text-center transition-all hover:shadow-lg">
                <i data-lucide="headphones" class="w-6 h-6 mx-auto mb-2"></i>
                <span class="text-sm font-medium">Support</span>
            </button>
        </div>
    </div>
</section>

<!-- Featured Jobs Section -->
<section id="jobs" class="py-24 bg-slate-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-end mb-12 gap-4">
            <div>
                <span class="text-blue-600 font-semibold tracking-wide uppercase text-sm">Opportunities</span>
                <h2 class="text-4xl font-bold text-slate-900 mt-2">Featured Jobs</h2>
                <p class="text-slate-600 mt-2">Hand-picked opportunities matching your skills</p>
            </div>
            <div class="flex gap-3">
                <select id="sortFilter" onchange="sortJobs()" class="px-4 py-2 rounded-lg border border-slate-200 bg-white text-slate-700 focus:ring-2 focus:ring-blue-500">
                    <option value="newest">Newest First</option>
                    <option value="salary-high">Highest Pay</option>
                    <option value="salary-low">Lowest Pay</option>
                </select>
                <button class="bg-blue-900 text-white px-6 py-2 rounded-lg font-medium hover:bg-blue-800 transition-colors">
                    View All Jobs
                </button>
            </div>
        </div>

        <!-- Jobs Grid -->
        <div id="jobsContainer" class="grid gap-6">
            <!-- Job cards will be injected here by JavaScript -->
        </div>

        <!-- Load More -->
        <div class="text-center mt-12">
            <button onclick="loadMoreJobs()" class="bg-white border-2 border-slate-200 text-slate-700 px-8 py-3 rounded-full font-semibold hover:border-blue-500 hover:text-blue-600 transition-all">
                Load More Jobs
            </button>
        </div>
    </div>
</section>

<!-- How It Works (For Freelancers) -->
<section id="how-it-works" class="py-24 bg-white relative overflow-hidden">
    <div class="absolute inset-0 bg-gradient-to-b from-slate-50 to-white pointer-events-none"></div>
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative">
        <div class="text-center max-w-3xl mx-auto mb-16">
            <span class="text-blue-600 font-semibold tracking-wide uppercase text-sm">Get Hired</span>
            <h2 class="text-4xl font-bold text-slate-900 mt-2 mb-4">Land Your Dream Gig in 3 Steps</h2>
            <p class="text-lg text-slate-600">Streamlined process designed to get you hired faster.</p>
        </div>

        <div class="grid md:grid-cols-3 gap-8 relative">
            <div class="hidden md:block absolute top-1/4 left-1/4 right-1/4 h-0.5 bg-gradient-to-r from-blue-200 via-blue-400 to-blue-600"></div>

            <div class="relative text-center">
                <div class="w-20 h-20 bg-blue-900 rounded-full flex items-center justify-center mx-auto mb-6 relative z-10 animate-pulse-glow">
                    <span class="text-3xl font-bold text-white">1</span>
                </div>
                <h3 class="text-xl font-bold text-slate-900 mb-3">Create Your Profile</h3>
                <p class="text-slate-600">Upload your resume, showcase your portfolio, and highlight your skills to stand out to top employers.</p>
            </div>

            <div class="relative text-center">
                <div class="w-20 h-20 bg-blue-700 rounded-full flex items-center justify-center mx-auto mb-6 relative z-10 animate-pulse-glow" style="animation-delay: 0.5s;">
                    <span class="text-3xl font-bold text-white">2</span>
                </div>
                <h3 class="text-xl font-bold text-slate-900 mb-3">Apply to Jobs</h3>
                <p class="text-slate-600">Browse vetted opportunities and apply with one click. Our AI matches you with perfect-fit projects.</p>
            </div>

            <div class="relative text-center">
                <div class="w-20 h-20 bg-blue-500 rounded-full flex items-center justify-center mx-auto mb-6 relative z-10 animate-pulse-glow" style="animation-delay: 1s;">
                    <span class="text-3xl font-bold text-white">3</span>
                </div>
                <h3 class="text-xl font-bold text-slate-900 mb-3">Get Paid</h3>
                <p class="text-slate-600">Work directly with clients through our secure platform with guaranteed payments and protection.</p>
            </div>
        </div>
    </div>
</section>

<!-- Top Hiring Companies -->
<section id="companies" class="py-24 bg-slate-900 text-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
            <h2 class="text-4xl font-bold mb-4">Top Hiring Companies</h2>
            <p class="text-slate-400 text-lg">Join these industry leaders on their next project</p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            <div class="bg-slate-800 rounded-2xl p-8 text-center hover:bg-slate-750 transition-all border border-slate-700">
                <div class="w-20 h-20 bg-blue-500/20 rounded-2xl flex items-center justify-center mx-auto mb-4">
                    <i data-lucide="cpu" class="w-10 h-10 text-blue-400"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">TechFlow</h3>
                <p class="text-slate-400 text-sm mb-4">Enterprise Software</p>
                <div class="flex items-center justify-center gap-4 text-sm">
                    <span class="text-green-400">24 Open Jobs</span>
                </div>
            </div>

            <div class="bg-slate-800 rounded-2xl p-8 text-center hover:bg-slate-750 transition-all border border-slate-700">
                <div class="w-20 h-20 bg-purple-500/20 rounded-2xl flex items-center justify-center mx-auto mb-4">
                    <i data-lucide="shopping-bag" class="w-10 h-10 text-purple-400"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">CommercePro</h3>
                <p class="text-slate-400 text-sm mb-4">E-commerce Platform</p>
                <div class="flex items-center justify-center gap-4 text-sm">
                    <span class="text-green-400">18 Open Jobs</span>
                </div>
            </div>

            <div class="bg-slate-800 rounded-2xl p-8 text-center hover:bg-slate-750 transition-all border border-slate-700">
                <div class="w-20 h-20 bg-cyan-500/20 rounded-2xl flex items-center justify-center mx-auto mb-4">
                    <i data-lucide="activity" class="w-10 h-10 text-cyan-400"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">DataSync</h3>
                <p class="text-slate-400 text-sm mb-4">Analytics & AI</p>
                <div class="flex items-center justify-center gap-4 text-sm">
                    <span class="text-green-400">31 Open Jobs</span>
                </div>
            </div>

            <div class="bg-slate-800 rounded-2xl p-8 text-center hover:bg-slate-750 transition-all border border-slate-700">
                <div class="w-20 h-20 bg-rose-500/20 rounded-2xl flex items-center justify-center mx-auto mb-4">
                    <i data-lucide="smartphone" class="w-10 h-10 text-rose-400"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">AppWorks</h3>
                <p class="text-slate-400 text-sm mb-4">Mobile Development</p>
                <div class="flex items-center justify-center gap-4 text-sm">
                    <span class="text-green-400">15 Open Jobs</span>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- CTA Section -->
<section class="py-24 bg-gradient-to-br from-blue-900 via-blue-800 to-slate-900 text-white relative overflow-hidden">
    <div class="absolute inset-0 bg-[url('data:image/svg+xml,%3Csvg%20width%3D%2260%22%20height%3D%2260%22%20viewBox%3D%220%200%2060%2060%22%20xmlns%3D%22http%3A//www.w3.org/2000/svg%22%3E%3Cg%20fill%3D%22none%22%20fill-rule%3D%22evenodd%22%3E%3Cg%20fill%3D%22%23ffffff%22%20fill-opacity%3D%220.03%22%3E%3Cpath%20d%3D%22M36%2034v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6%2034v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6%204V0H4v4H0v2h4v4h2V6h4V4H6z%22/%3E%3C/g%3E%3C/g%3E%3C/svg%3E')] opacity-20"></div>
    
    <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center relative">
        <h2 class="text-4xl md:text-5xl font-bold mb-6">Ready to Find Your Next Gig?</h2>
        <p class="text-xl text-blue-100 mb-10 max-w-2xl mx-auto">Join 50,000+ freelancers already working with top companies. Upload your resume and get matched today.</p>
        
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <button class="bg-white text-blue-900 px-8 py-4 rounded-full font-bold text-lg hover:bg-blue-50 transition-all hover:shadow-xl hover:scale-105 flex items-center justify-center gap-2">
                <i data-lucide="upload" class="w-5 h-5"></i>
                Upload Resume
            </button>
            <button class="border-2 border-white text-white px-8 py-4 rounded-full font-bold text-lg hover:bg-white/10 transition-all">
                Browse All Jobs
            </button>
        </div>

        <p class="mt-6 text-blue-200 text-sm">Free to join • Get hired in 48 hours • Secure payments</p>
    </div>
</section>

<!-- Footer -->
<footer class="bg-slate-950 text-slate-400 py-16 border-t border-slate-900">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid md:grid-cols-2 lg:grid-cols-5 gap-12 mb-12">
            <div class="lg:col-span-2">
                <div class="flex items-center gap-2 mb-6">
                    <div class="w-10 h-10 bg-gradient-to-br from-blue-900 to-blue-600 rounded-lg flex items-center justify-center">
                        <i data-lucide="hexagon" class="w-6 h-6 text-white"></i>
                    </div>
                    <span class="text-2xl font-bold text-white tracking-tight">Task<span class="text-blue-500">Flow</span></span>
                </div>
                <p class="mb-6 max-w-sm">The premier marketplace for elite freelance talent. Connecting top professionals with world-class companies.</p>
                <div class="flex gap-4">
                    <a href="#" class="w-10 h-10 bg-slate-900 rounded-full flex items-center justify-center hover:bg-blue-600 hover:text-white transition-all">
                        <i data-lucide="twitter" class="w-5 h-5"></i>
                    </a>
                    <a href="#" class="w-10 h-10 bg-slate-900 rounded-full flex items-center justify-center hover:bg-blue-600 hover:text-white transition-all">
                        <i data-lucide="linkedin" class="w-5 h-5"></i>
                    </a>
                    <a href="#" class="w-10 h-10 bg-slate-900 rounded-full flex items-center justify-center hover:bg-blue-600 hover:text-white transition-all">
                        <i data-lucide="github" class="w-5 h-5"></i>
                    </a>
                </div>
            </div>

            <div>
                <h4 class="text-white font-semibold mb-4">For Freelancers</h4>
                <ul class="space-y-3">
                    <li><a href="#" class="hover:text-white transition-colors">Browse Jobs</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Submit Resume</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Freelancer Guides</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Success Stories</a></li>
                </ul>
            </div>

            <div>
                <h4 class="text-white font-semibold mb-4">For Companies</h4>
                <ul class="space-y-3">
                    <li><a href="#" class="hover:text-white transition-colors">Post a Job</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Enterprise</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Recruiting Solutions</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Pricing</a></li>
                </ul>
            </div>

            <div>
                <h4 class="text-white font-semibold mb-4">Resources</h4>
                <ul class="space-y-3">
                    <li><a href="#" class="hover:text-white transition-colors">Help Center</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Blog</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Community</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Contact Us</a></li>
                </ul>
            </div>
        </div>

        <div class="pt-8 border-t border-slate-900 flex flex-col md:flex-row justify-between items-center gap-4">
            <p class="text-sm">© 2024 TaskFlow Inc. All rights reserved.</p>
            <div class="flex gap-6 text-sm">
                <a href="#" class="hover:text-white transition-colors">Privacy Policy</a>
                <a href="#" class="hover:text-white transition-colors">Terms of Service</a>
                <a href="#" class="hover:text-white transition-colors">Cookie Settings</a>
            </div>
        </div>
    </div>
</footer>

<!-- Application Modal -->
<div id="applyModal" class="fixed inset-0 z-50 hidden overflow-y-auto" aria-labelledby="modal-title" role="dialog" aria-modal="true">
    <div class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
        <div class="fixed inset-0 bg-slate-900/75 transition-opacity" aria-hidden="true" onclick="closeModal()"></div>
        <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
        <div class="inline-block align-bottom bg-white rounded-2xl text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg w-full">
            <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                <div class="sm:flex sm:items-start">
                    <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left w-full">
                        <h3 class="text-2xl leading-6 font-bold text-slate-900 mb-2" id="modal-job-title">Job Title</h3>
                        <p class="text-sm text-slate-500 mb-6" id="modal-company">Company Name</p>
                        
                        <form id="applicationForm" class="space-y-4">
                            <div>
                                <label class="block text-sm font-medium text-slate-700 mb-1">Full Name</label>
                                <input type="text" required class="w-full px-4 py-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-slate-700 mb-1">Email Address</label>
                                <input type="email" required class="w-full px-4 py-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-slate-700 mb-1">Phone Number</label>
                                <input type="tel" class="w-full px-4 py-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-slate-700 mb-1">Resume/CV</label>
                                <div class="mt-1 flex justify-center px-6 pt-5 pb-6 border-2 border-slate-300 border-dashed rounded-lg hover:border-blue-500 transition-colors cursor-pointer">
                                    <div class="space-y-1 text-center">
                                        <i data-lucide="upload-cloud" class="mx-auto h-12 w-12 text-slate-400"></i>
                                        <div class="flex text-sm text-slate-600">
                                            <label class="relative cursor-pointer bg-white rounded-md font-medium text-blue-600 hover:text-blue-500 focus-within:outline-none">
                                                <span>Upload a file</span>
                                                <input type="file" class="sr-only" accept=".pdf,.doc,.docx">
                                            </label>
                                            <p class="pl-1">or drag and drop</p>
                                        </div>
                                        <p class="text-xs text-slate-500">PDF, DOC up to 10MB</p>
                                    </div>
                                </div>
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-slate-700 mb-1">Cover Letter (Optional)</label>
                                <textarea rows="3" class="w-full px-4 py-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent" placeholder="Tell us why you're perfect for this role..."></textarea>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
            <div class="bg-slate-50 px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
                <button type="button" onclick="submitApplication()" class="w-full inline-flex justify-center rounded-lg border border-transparent shadow-sm px-4 py-2 bg-blue-900 text-base font-medium text-white hover:bg-blue-800 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 sm:ml-3 sm:w-auto sm:text-sm">
                    Submit Application
                </button>
                <button type="button" onclick="closeModal()" class="mt-3 w-full inline-flex justify-center rounded-lg border border-slate-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-slate-700 hover:bg-slate-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm">
                    Cancel
                </button>
            </div>
        </div>
    </div>
</div>

<!-- Success Toast -->
<div id="successToast" class="fixed bottom-5 right-5 bg-green-500 text-white px-6 py-4 rounded-lg shadow-xl transform translate-y-20 opacity-0 transition-all duration-300 z-50 flex items-center gap-3">
    <i data-lucide="check-circle" class="w-6 h-6"></i>
    <div>
        <div class="font-semibold">Application Submitted!</div>
        <div class="text-sm text-green-100">Good luck with your application.</div>
    </div>
</div>

<script>
    // Job Data
    const jobs = [
        {
            id: 1,
            title: "Senior React Developer",
            company: "TechFlow Systems",
            logo: "cpu",
            category: "development",
            type: "Full-time",
            location: "Remote",
            salary: "$120 - $150/hr",
            posted: "2 hours ago",
            description: "We're seeking an experienced React developer to lead our frontend team. You'll be working on scalable enterprise applications with modern tech stack.",
            skills: ["React", "TypeScript", "Node.js", "GraphQL"],
            badge: "hot",
            color: "blue"
        },
        {
            id: 2,
            title: "UX/UI Designer",
            company: "DesignStudio Pro",
            logo: "palette",
            category: "design",
            type: "Contract",
            location: "Remote",
            salary: "$90 - $120/hr",
            posted: "5 hours ago",
            description: "Join our creative team to design intuitive user experiences for fintech applications. Strong portfolio and Figma expertise required.",
            skills: ["Figma", "Adobe XD", "Prototyping", "User Research"],
            badge: "featured",
            color: "purple"
        },
        {
            id: 3,
            title: "Machine Learning Engineer",
            company: "DataSync AI",
            logo: "brain",
            category: "ai",
            type: "Full-time",
            location: "Hybrid (NY)",
            salary: "$140 - $180/hr",
            posted: "1 day ago",
            description: "Build and deploy ML models for predictive analytics. Experience with Python, TensorFlow, and cloud platforms essential.",
            skills: ["Python", "TensorFlow", "AWS", "SQL"],
            badge: "new",
            color: "cyan"
        },
        {
            id: 4,
            title: "Content Marketing Manager",
            company: "GrowthRocket",
            logo: "megaphone",
            category: "marketing",
            type: "Part-time",
            location: "Remote",
            salary: "$60 - $80/hr",
            posted: "3 hours ago",
            description: "Develop content strategy and manage editorial calendar for B2B SaaS company. SEO and content marketing experience required.",
            skills: ["SEO", "Content Strategy", "Copywriting", "Analytics"],
            badge: "urgent",
            color: "amber"
        },
        {
            id: 5,
            title: "Technical Writer",
            company: "DocuTech",
            logo: "pen-tool",
            category: "writing",
            type: "Contract",
            location: "Remote",
            salary: "$50 - $70/hr",
            posted: "1 day ago",
            description: "Create clear technical documentation for API products. Background in software development preferred.",
            skills: ["Technical Writing", "API Docs", "Markdown", "Git"],
            badge: null,
            color: "rose"
        },
        {
            id: 6,
            title: "Virtual Assistant",
            company: "ExecSupport",
            logo: "clipboard-list",
            category: "admin",
            type: "Part-time",
            location: "Remote",
            salary: "$25 - $35/hr",
            posted: "4 hours ago",
            description: "Support C-level executives with calendar management, email handling, and travel coordination.",
            skills: ["Calendar Management", "Communication", "Organization", "G-Suite"],
            badge: "new",
            color: "green"
        },
        {
            id: 7,
            title: "Customer Success Manager",
            company: "SaaS Solutions Inc",
            logo: "headphones",
            category: "customer",
            type: "Full-time",
            location: "Remote (US)",
            salary: "$70 - $90/hr",
            posted: "2 days ago",
            description: "Manage enterprise client relationships and ensure successful product adoption. 3+ years experience required.",
            skills: ["CRM", "Account Management", "Problem Solving", "Communication"],
            badge: null,
            color: "indigo"
        },
        {
            id: 8,
            title: "DevOps Engineer",
            company: "CloudFirst",
            logo: "cloud",
            category: "development",
            type: "Full-time",
            location: "Remote",
            salary: "$130 - $160/hr",
            posted: "6 hours ago",
            description: "Implement CI/CD pipelines and manage cloud infrastructure. Kubernetes and Terraform experience required.",
            skills: ["Kubernetes", "Docker", "AWS", "Terraform"],
            badge: "hot",
            color: "blue"
        }
    ];

    let currentFilter = 'all';
    let currentJobs = [...jobs];

    // Initialize
    document.addEventListener('DOMContentLoaded', () => {
        lucide.createIcons();
        renderJobs();
    });

    // Render Jobs
    function renderJobs() {
        const container = document.getElementById('jobsContainer');
        container.innerHTML = currentJobs.map(job => `
            <div class="bg-white rounded-2xl p-6 hover-lift border border-slate-100 group relative overflow-hidden">
                ${job.badge ? `
                    <div class="absolute top-4 right-4">
                        <span class="px-3 py-1 ${getBadgeClass(job.badge)} rounded-full text-xs font-semibold uppercase tracking-wide">
                            ${job.badge}
                        </span>
                    </div>
                ` : ''}
                
                <div class="flex flex-col md:flex-row md:items-center gap-6">
                    <div class="flex-shrink-0">
                        <div class="w-16 h-16 bg-${job.color}-100 rounded-2xl flex items-center justify-center">
                            <i data-lucide="${job.logo}" class="w-8 h-8 text-${job.color}-600"></i>
                        </div>
                    </div>
                    
                    <div class="flex-1">
                        <div class="flex flex-col md:flex-row md:items-center gap-2 md:gap-4 mb-2">
                            <h3 class="text-xl font-bold text-slate-900 group-hover:text-blue-600 transition-colors">${job.title}</h3>
                            <span class="text-slate-400">•</span>
                            <span class="text-slate-600 font-medium">${job.company}</span>
                        </div>
                        
                        <p class="text-slate-600 mb-4 line-clamp-2">${job.description}</p>
                        
                        <div class="flex flex-wrap items-center gap-4 text-sm text-slate-500 mb-4">
                            <span class="flex items-center gap-1">
                                <i data-lucide="map-pin" class="w-4 h-4"></i>
                                ${job.location}
                            </span>
                            <span class="flex items-center gap-1">
                                <i data-lucide="clock" class="w-4 h-4"></i>
                                ${job.type}
                            </span>
                            <span class="flex items-center gap-1">
                                <i data-lucide="calendar" class="w-4 h-4"></i>
                                ${job.posted}
                            </span>
                            <span class="flex items-center gap-1 font-semibold text-green-600">
                                <i data-lucide="dollar-sign" class="w-4 h-4"></i>
                                ${job.salary}
                            </span>
                        </div>
                        
                        <div class="flex flex-wrap gap-2">
                            ${job.skills.map(skill => `
                                <span class="px-3 py-1 bg-slate-100 text-slate-700 rounded-lg text-xs font-medium">${skill}</span>
                            `).join('')}
                        </div>
                    </div>
                    
                    <div class="flex-shrink-0 flex flex-col gap-3">
                        <button onclick="openApplyModal(${job.id})" class="bg-blue-900 hover:bg-blue-800 text-white px-6 py-3 rounded-xl font-semibold transition-all hover:shadow-lg whitespace-nowrap">
                            Apply Now
                        </button>
                        <button class="text-slate-500 hover:text-blue-600 font-medium text-sm flex items-center justify-center gap-1">
                            <i data-lucide="bookmark" class="w-4 h-4"></i>
                            Save
                        </button>
                    </div>
                </div>
            </div>
        `).join('');
        
        lucide.createIcons();
    }

    function getBadgeClass(badge) {
        const classes = {
            'hot': 'bg-red-100 text-red-800',
            'new': 'bg-green-100 text-green-800',
            'featured': 'bg-purple-100 text-purple-800',
            'urgent': 'bg-orange-100 text-orange-800'
        };
        return classes[badge] || 'bg-slate-100 text-slate-800';
    }

    // Filter Jobs
    function filterJobs(category) {
        currentFilter = category;
        
        // Update button styles
        document.querySelectorAll('.category-btn').forEach(btn => {
            btn.classList.remove('bg-blue-900', 'text-white', 'border-blue-900');
            btn.classList.add('text-slate-700', 'border-slate-200');
        });
        event.target.closest('.category-btn').classList.remove('text-slate-700', 'border-slate-200');
        event.target.closest('.category-btn').classList.add('bg-blue-900', 'text-white', 'border-blue-900');
        
        // Filter logic
        if (category === 'all') {
            currentJobs = [...jobs];
        } else {
            currentJobs = jobs.filter(job => job.category === category);
        }
        
        renderJobs();
    }

    // Sort Jobs
    function sortJobs() {
        const sortValue = document.getElementById('sortFilter').value;
        
        if (sortValue === 'salary-high') {
            currentJobs.sort((a, b) => {
                const aSalary = parseInt(a.salary.match(/\d+/)[0]);
                const bSalary = parseInt(b.salary.match(/\d+/)[0]);
                return bSalary - aSalary;
            });
        } else if (sortValue === 'salary-low') {
            currentJobs.sort((a, b) => {
                const aSalary = parseInt(a.salary.match(/\d+/)[0]);
                const bSalary = parseInt(b.salary.match(/\d+/)[0]);
                return aSalary - bSalary;
            });
        } else if (sortValue === 'newest') {
            currentJobs.sort((a, b) => a.id - b.id);
        }
        
        renderJobs();
    }

    // Search Jobs
    document.getElementById('jobSearch')?.addEventListener('input', (e) => {
        const searchTerm = e.target.value.toLowerCase();
        if (searchTerm === '') {
            currentJobs = currentFilter === 'all' ? [...jobs] : jobs.filter(job => job.category === currentFilter);
        } else {
            currentJobs = jobs.filter(job => 
                job.title.toLowerCase().includes(searchTerm) || 
                job.company.toLowerCase().includes(searchTerm) ||
                job.skills.some(skill => skill.toLowerCase().includes(searchTerm))
            );
        }
        renderJobs();
    });

    // Modal Functions
    function openApplyModal(jobId) {
        const job = jobs.find(j => j.id === jobId);
        if (job) {
            document.getElementById('modal-job-title').textContent = job.title;
            document.getElementById('modal-company').textContent = job.company;
            document.getElementById('applyModal').classList.remove('hidden');
            document.body.style.overflow = 'hidden';
        }
    }

    function closeModal() {
        document.getElementById('applyModal').classList.add('hidden');
        document.body.style.overflow = 'auto';
        document.getElementById('applicationForm').reset();
    }

    function submitApplication() {
        const form = document.getElementById('applicationForm');
        if (form.checkValidity()) {
            closeModal();
            showSuccessToast();
        } else {
            form.reportValidity();
        }
    }

    function showSuccessToast() {
        const toast = document.getElementById('successToast');
        toast.classList.remove('translate-y-20', 'opacity-0');
        setTimeout(() => {
            toast.classList.add('translate-y-20', 'opacity-0');
        }, 3000);
    }

    // Utility Functions
    function scrollToJobs() {
        document.getElementById('jobs').scrollIntoView({ behavior: 'smooth' });
    }

    function loadMoreJobs() {
        // Simulate loading more jobs
        const btn = event.target;
        btn.innerHTML = '<i data-lucide="loader-2" class="w-5 h-5 animate-spin inline"></i> Loading...';
        lucide.createIcons();
        
        setTimeout(() => {
            btn.innerHTML = 'Load More Jobs';
            // In real implementation, this would fetch more jobs from API
            alert('In production, this would load more job listings from the database.');
        }, 1000);
    }

    function toggleMobileMenu() {
        const menu = document.getElementById('mobile-menu');
        const icon = document.getElementById('menu-icon');
        
        if (menu.classList.contains('hidden')) {
            menu.classList.remove('hidden');
            icon.setAttribute('data-lucide', 'x');
        } else {
            menu.classList.add('hidden');
            icon.setAttribute('data-lucide', 'menu');
        }
        lucide.createIcons();
    }

    // Navbar scroll effect
    window.addEventListener('scroll', () => {
        const navbar = document.getElementById('navbar');
        if (window.scrollY > 50) {
            navbar.classList.add('shadow-md');
        } else {
            navbar.classList.remove('shadow-md');
        }
    });

    // Close modal on escape key
    document.addEventListener('keydown', (e) => {
        if (e.key === 'Escape') closeModal();
    });
</script>

