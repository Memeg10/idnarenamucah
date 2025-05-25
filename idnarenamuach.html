function changeBackground(theme) {
    const body = document.body;
    
    // Remove existing background classes
    body.classList.remove('bg-casino', 'bg-luxury', 'bg-neon', 'bg-poker');
    
    if (theme === 'custom') {
        const url = prompt('Enter image URL:');
        if (url) {
            body.style.backgroundImage = `url('${url}')`;
        }
    } else {
        // Reset custom styles
        body.style.backgroundImage = '';
        
        // Apply theme class
        body.classList.add(`bg-${theme}`);
    }

    // Auto-collapse after selection on all devices
    setTimeout(() => {
        collapseBgControls();
    }, 500);
}

// Toggle background controls
function toggleBgControls() {
    const bgControls = document.getElementById('bgControls');
    const collapseTimer = document.getElementById('collapseTimer');
    
    if (bgControls.classList.contains('collapsed')) {
        expandBgControls();
    } else {
        collapseBgControls();
    }
}

// Expand background controls
function expandBgControls() {
    const bgControls = document.getElementById('bgControls');
    const collapseTimer = document.getElementById('collapseTimer');
    
    bgControls.classList.remove('collapsed');
    bgControls.classList.add('expanded');
    
    // Start auto-collapse timer (3 seconds)
    startCollapseTimer();
}

// Collapse background controls
function collapseBgControls() {
    const bgControls = document.getElementById('bgControls');
    const collapseTimer = document.getElementById('collapseTimer');
    
    bgControls.classList.remove('expanded');
    bgControls.classList.add('collapsed');
    
    // Clear timer
    clearCollapseTimer();
}

// Start collapse timer
function startCollapseTimer() {
    if (isMouseOver) return; // Don't start timer if mouse is over the control
    
    clearCollapseTimer(); // Clear any existing timer
    
    const collapseTimer = document.getElementById('collapseTimer');
    collapseTimer.classList.add('active');
    
    collapseTimeout = setTimeout(() => {
        if (!isMouseOver) {
            collapseBgControls();
        }
    }, 3000);
}

// Clear collapse timer
function clearCollapseTimer() {
    const collapseTimer = document.getElementById('collapseTimer');
    collapseTimer.classList.remove('active');
    
    if (collapseTimeout) {
        clearTimeout(collapseTimeout);
        collapseTimeout = null;
    }
}

// Mouse enter/leave events to pause auto-collapse
document.getElementById('bgControls').addEventListener('mouseenter', () => {
    isMouseOver = true;
    clearCollapseTimer();
});

document.getElementById('bgControls').addEventListener('mouseleave', () => {
    isMouseOver = false;
    const bgControls = document.getElementById('bgControls');
    if (bgControls.classList.contains('expanded')) {
        startCollapseTimer();
    }
});

// Close background controls when clicking outside
document.addEventListener('click', (e) => {
    const bgControls = document.getElementById('bgControls');
    const isClickInside = bgControls.contains(e.target);
    
    if (!isClickInside && bgControls.classList.contains('expanded')) {
        collapseBgControls();
    }
});

// Handle window resize
window.addEventListener('resize', () => {
    // Reset state on resize
    clearCollapseTimer();
});

// Keyboard shortcuts
document.addEventListener('keydown', (e) => {
    // Press 'B' to toggle background controls
    if (e.key.toLowerCase() === 'b' && !e.ctrlKey && !e.altKey && !e.shiftKey) {
        // Only if not typing in an input field
        if (document.activeElement.tagName !== 'INPUT' && document.activeElement.tagName !== 'TEXTAREA') {
            toggleBgControls();
        }
    }
    
    // Press 'Escape' to close if expanded
    if (e.key === 'Escape') {
        const bgControls = document.getElementById('bgControls');
        if (bgControls.classList.contains('expanded')) {
            collapseBgControls();
        }
    }
});

// Initialize state
document.addEventListener('DOMContentLoaded', () => {
    const bgControls = document.getElementById('bgControls');
    bgControls.classList.add('collapsed');
});

// Touch events for mobile
let touchStartTime = 0;
document.getElementById('bgControls').addEventListener('touchstart', () => {
    touchStartTime = Date.now();
});

document.getElementById('bgControls').addEventListener('touchend', (e) => {
    const touchDuration = Date.now() - touchStartTime;
    // Long press (500ms+) to keep expanded longer on mobile
    if (touchDuration > 500) {
        clearCollapseTimer();
        // Restart timer after 5 seconds instead of 3 for long press
        setTimeout(() => {
            if (!isMouseOver) {
                const bgControls = document.getElementById('bgControls');
                if (bgControls.classList.contains('expanded')) {
                    startCollapseTimer();
                }
            }
        }, 2000);
    }
});

// ======= FLOATING MINI SLOT FUNCTIONALITY =======
const slotSymbols = ['🍎', '🍋', '🍒', '🍇', '🔔', '💎', '⭐', '7️⃣', '🍊', '🥝'];
let isSpinning = false;
let slotCollapseTimeout = null;
let isSlotMouseOver = false;
let isDragging = false;
let dragOffset = { x: 0, y: 0 };

// Initialize slot when page loads
document.addEventListener('DOMContentLoaded', function() {
    initializeSlot();
    setupSlotDragAndDrop();
    setupSlotAutoCollapse();
    
    // Auto-spin every 8 seconds
    setInterval(autoSlotSpin, 8000);
});

function initializeSlot() {
    const miniSlot = document.getElementById('miniSlot');
    
    // Start collapsed on desktop
    if (window.innerWidth > 768) {
        miniSlot.classList.add('collapsed');
        loadSlotSavedPosition();
    } else {
        miniSlot.classList.remove('collapsed');
        miniSlot.classList.add('expanded');
    }
}

// Toggle slot expand/collapse
function toggleSlot() {
    const miniSlot = document.getElementById('miniSlot');
    
    if (miniSlot.classList.contains('collapsed')) {
        expandSlot();
    } else {
        collapseSlot();
    }
}

// Expand slot
function expandSlot() {
    const miniSlot = document.getElementById('miniSlot');
    
    miniSlot.classList.remove('collapsed');
    miniSlot.classList.add('expanded');
    
    // Start auto-collapse timer
    startSlotCollapseTimer();
}

// Collapse slot
function collapseSlot() {
    const miniSlot = document.getElementById('miniSlot');
    
    miniSlot.classList.remove('expanded');
    miniSlot.classList.add('collapsed');
    
    // Clear timer
    clearSlotCollapseTimer();
}

// Prevent click outside when clicking inside slot
function handleSlotClick(e) {
    e.stopPropagation();
}

// Auto-collapse setup
function setupSlotAutoCollapse() {
    const miniSlot = document.getElementById('miniSlot');
    
    // Mouse enter/leave events
    miniSlot.addEventListener('mouseenter', () => {
        isSlotMouseOver = true;
        clearSlotCollapseTimer();
    });

    miniSlot.addEventListener('mouseleave', () => {
        isSlotMouseOver = false;
        if (miniSlot.classList.contains('expanded') && !isDragging) {
            startSlotCollapseTimer();
        }
    });

    // Click outside to close (only on desktop)
    document.addEventListener('click', (e) => {
        if (window.innerWidth > 768) {
            const isClickInsideSlot = miniSlot.contains(e.target);
            const isSlotExpanded = miniSlot.classList.contains('expanded');
            
            if (!isClickInsideSlot && isSlotExpanded && !isDragging) {
                collapseSlot();
            }
        }
    });

    // Touch outside to close (mobile/tablet)
    document.addEventListener('touchstart', (e) => {
        if (window.innerWidth > 768) {
            const isClickInsideSlot = miniSlot.contains(e.target);
            const isSlotExpanded = miniSlot.classList.contains('expanded');
            
            if (!isClickInsideSlot && isSlotExpanded && !isDragging) {
                collapseSlot();
            }
        }
    });

    // Handle window resize
    window.addEventListener('resize', () => {
        if (window.innerWidth <= 768) {
            miniSlot.classList.remove('collapsed');
            miniSlot.classList.add('expanded');
            clearSlotCollapseTimer();
        } else if (window.innerWidth > 768 && !miniSlot.classList.contains('expanded')) {
            miniSlot.classList.add('collapsed');
        }
    });
}

// Start collapse timer
function startSlotCollapseTimer() {
    if (isSlotMouseOver || isDragging || window.innerWidth <= 768) return;
    
    clearSlotCollapseTimer();
    
    const collapseTimer = document.getElementById('slotCollapseTimer');
    if (collapseTimer) {
        collapseTimer.classList.add('active');
    }
    
    slotCollapseTimeout = setTimeout(() => {
        if (!isSlotMouseOver && !isDragging) {
            collapseSlot();
        }
    }, 3000);
}

// Clear collapse timer
function clearSlotCollapseTimer() {
    const collapseTimer = document.getElementById('slotCollapseTimer');
    if (collapseTimer) {
        collapseTimer.classList.remove('active');
    }
    
    if (slotCollapseTimeout) {
        clearTimeout(slotCollapseTimeout);
        slotCollapseTimeout = null;
    }
}

// Drag and drop functionality
function setupSlotDragAndDrop() {
    const miniSlot = document.getElementById('miniSlot');
    let startPos = { x: 0, y: 0 };
    let currentPos = { x: 0, y: 0 };

    // Mouse events
    miniSlot.addEventListener('mousedown', startDrag);
    document.addEventListener('mousemove', drag);
    document.addEventListener('mouseup', endDrag);

    // Touch events
    miniSlot.addEventListener('touchstart', startDrag);
    document.addEventListener('touchmove', drag);
    document.addEventListener('touchend', endDrag);

    function startDrag(e) {
        if (window.innerWidth <= 768) return; // Disable drag on mobile
        if (e.target.closest('.spin-btn') || e.target.closest('.slot-toggle')) return; // Don't drag when clicking buttons
        
        // Prevent click outside detection while dragging
        e.stopPropagation();
        
        isDragging = true;
        miniSlot.classList.add('dragging');
        clearSlotCollapseTimer();

        const clientX = e.clientX || (e.touches && e.touches[0].clientX);
        const clientY = e.clientY || (e.touches && e.touches[0].clientY);
        
        const rect = miniSlot.getBoundingClientRect();
        dragOffset.x = clientX - rect.left;
        dragOffset.y = clientY - rect.top;

        startPos.x = clientX;
        startPos.y = clientY;

        e.preventDefault();
    }

    function drag(e) {
        if (!isDragging) return;

        const clientX = e.clientX || (e.touches && e.touches[0].clientX);
        const clientY = e.clientY || (e.touches && e.touches[0].clientY);

        currentPos.x = clientX - dragOffset.x;
        currentPos.y = clientY - dragOffset.y;

        // Constrain to viewport
        const maxX = window.innerWidth - miniSlot.offsetWidth;
        const maxY = window.innerHeight - miniSlot.offsetHeight;

        currentPos.x = Math.max(0, Math.min(maxX, currentPos.x));
        currentPos.y = Math.max(0, Math.min(maxY, currentPos.y));

        miniSlot.style.left = currentPos.x + 'px';
        miniSlot.style.top = currentPos.y + 'px';
        miniSlot.style.bottom = 'auto';

        e.preventDefault();
    }

    function endDrag(e) {
        if (!isDragging) return;

        isDragging = false;
        miniSlot.classList.remove('dragging');

        // Snap to edges
        snapSlotToEdge();
        
        // Save position
        saveSlotPosition();

        // Check if it was just a click (not a drag)
        const clientX = e.clientX || (e.changedTouches && e.changedTouches[0].clientX);
        const clientY = e.clientY || (e.changedTouches && e.changedTouches[0].clientY);
        
        if (clientX && clientY) {
            const dragDistance = Math.sqrt(
                Math.pow(clientX - startPos.x, 2) + 
                Math.pow(clientY - startPos.y, 2)
            );

            // If it was just a click (small drag distance), toggle slot
            if (dragDistance < 10 && miniSlot.classList.contains('collapsed')) {
                expandSlot();
            }
        }
    }
}

// Snap to viewport edges
function snapSlotToEdge() {
    const miniSlot = document.getElementById('miniSlot');
    const rect = miniSlot.getBoundingClientRect();
    const snapDistance = 20;
    
    let newPos = {
        x: rect.left,
        y: rect.top
    };

    // Snap to left/right edges
    if (rect.left < snapDistance) {
        newPos.x = 20;
    } else if (rect.right > window.innerWidth - snapDistance) {
        newPos.x = window.innerWidth - rect.width - 20;
    }

    // Snap to top/bottom edges
    if (rect.top < snapDistance) {
        newPos.y = 20;
    } else if (rect.bottom > window.innerHeight - snapDistance) {
        newPos.y = window.innerHeight - rect.height - 20;
    }

    // Apply smooth transition
    miniSlot.classList.add('repositioning');
    miniSlot.style.left = newPos.x + 'px';
    miniSlot.style.top = newPos.y + 'px';
    miniSlot.style.bottom = 'auto';

    setTimeout(() => {
        miniSlot.classList.remove('repositioning');
    }, 300);
}

// Save position to localStorage
function saveSlotPosition() {
    const miniSlot = document.getElementById('miniSlot');
    const position = {
        x: parseFloat(miniSlot.style.left) || 20,
        y: parseFloat(miniSlot.style.top) || 20
    };
    localStorage.setItem('miniSlotPosition', JSON.stringify(position));
}

// Load saved position
function loadSlotSavedPosition() {
    const saved = localStorage.getItem('miniSlotPosition');
    if (saved) {
        const position = JSON.parse(saved);
        const miniSlot = document.getElementById('miniSlot');
        
        // Validate position is still within viewport
        const maxX = window.innerWidth - 220; // approximate slot width
        const maxY = window.innerHeight - 200; // approximate slot height
        
        if (position.x <= maxX && position.y <= maxY) {
            miniSlot.style.left = position.x + 'px';
            miniSlot.style.top = position.y + 'px';
            miniSlot.style.bottom = 'auto';
        }
    }
}

// Auto spin function
function autoSlotSpin() {
    if (!isSpinning && window.innerWidth > 768) {
        spinSlot();
    }
}

// Manual spin function
function manualSpin() {
    if (!isSpinning) {
        spinSlot();
    }
}

// Main slot spinning logic
function spinSlot() {
    if (isSpinning) return;
    
    isSpinning = true;
    const spinBtn = document.getElementById('spinBtn');
    const result = document.getElementById('slotResult');
    const reel1 = document.getElementById('reel1');
    const reel2 = document.getElementById('reel2');
    const reel3 = document.getElementById('reel3');
    
    // Disable button and update text
    spinBtn.disabled = true;
    spinBtn.textContent = 'SPINNING...';
    result.textContent = 'Berputar...';
    result.className = 'slot-result';
    
    // Add spinning animation
    reel1.classList.add('spinning');
    reel2.classList.add('spinning');
    reel3.classList.add('spinning');
    
    // Spinning animation
    const spinInterval = setInterval(() => {
        reel1.textContent = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
        reel2.textContent = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
        reel3.textContent = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
    }, 100);
    
    setTimeout(() => {
        clearInterval(spinInterval);
        
        // Remove spinning animation
        reel1.classList.remove('spinning');
        reel2.classList.remove('spinning');
        reel3.classList.remove('spinning');
        
        // Determine final result with weighted probability
        let final1, final2, final3;
        const random = Math.random();
        
        if (random < 0.05) { // 5% chance for jackpot
            final1 = final2 = final3 = '7️⃣';
            result.textContent = '🎉 MEGA JACKPOT! 🎉';
            result.className = 'slot-result jackpot';
            createMegaWin();
        } else if (random < 0.15) { // 10% chance for triple match
            const symbol = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
            final1 = final2 = final3 = symbol;
            result.textContent = '💰 JACKPOT! 💰';
            result.className = 'slot-result win';
        } else if (random < 0.35) { // 20% chance for double match
            final1 = final2 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
            final3 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
            result.textContent = '✨ Menang! ✨';
            result.className = 'slot-result win';
        } else { // 65% chance for no match
            final1 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
            final2 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
            final3 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)];
            result.textContent = 'Coba lagi...';
            result.className = 'slot-result';
        }
        
        reel1.textContent = final1;
        reel2.textContent = final2;
        reel3.textContent = final3;
        
        // Re-enable button
        spinBtn.disabled = false;
        spinBtn.textContent = 'SPIN';
        isSpinning = false;
        
        // Auto-expand if collapsed and won
        if (result.className.includes('win') || result.className.includes('jackpot')) {
            const miniSlot = document.getElementById('miniSlot');
            if (miniSlot.classList.contains('collapsed')) {
                expandSlot();
            }
        }
    }, 2000);
}

// ======= JACKPOT AND WIDGETS FUNCTIONALITY =======
let jackpotAmount = 2500000000;
let onlineUsers = Math.floor(Math.random() * 500) + 1200;
let countdownTime = 3600; // 1 hour in seconds

// Initialize everything when page loads
document.addEventListener('DOMContentLoaded', function() {
    updateJackpot();
    updateOnlineCount();
    updateCountdown();
    
    // Set intervals for updates
    setInterval(updateJackpot, 2000);
    setInterval(updateOnlineCount, 5000);
    setInterval(updateCountdown, 1000);
    setInterval(createWinNotification, Math.random() * 5000 + 3000);
    setInterval(updatePlayersActivity, 30000);
    
    // Initial win notification
    setTimeout(createWinNotification, 2000);
});

// Update jackpot amount
function updateJackpot() {
    jackpotAmount += Math.floor(Math.random() * 100000) + 50000;
    const jackpotElement = document.getElementById('jackpotAmount');
    if (jackpotElement) {
        jackpotElement.textContent = 'Rp ' + jackpotAmount.toLocaleString('id-ID');
    }
}

// Update online users count
function updateOnlineCount() {
    const change = Math.floor(Math.random() * 20) - 10;
    onlineUsers = Math.max(1000, onlineUsers + change);
    const onlineElement = document.getElementById('onlineCount');
    if (onlineElement) {
        onlineElement.textContent = onlineUsers.toLocaleString('id-ID');
    }
}

// Update countdown timer
function updateCountdown() {
    countdownTime--;
    if (countdownTime <= 0) {
        countdownTime = 3600; // Reset to 1 hour
        // Trigger jackpot reset effect
        createJackpotReset();
    }
    
    const hours = Math.floor(countdownTime / 3600);
    const minutes = Math.floor((countdownTime % 3600) / 60);
    const seconds = countdownTime % 60;
    
    const timerElement = document.getElementById('countdownTimer');
    if (timerElement) {
        timerElement.textContent = 
            `Reset dalam: ${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
    }
}

// Update players activity message
function updatePlayersActivity() {
    const activities = [
        '+12 bergabung dalam 5 menit',
        '+8 pemain menang besar',
        '+15 sedang bermain slot',
        '+5 bermain live casino',
        '+20 login dalam 10 menit',
        '+7 melakukan withdraw',
        '+10 mendapat jackpot kecil'
    ];
    
    const randomActivity = activities[Math.floor(Math.random() * activities.length)];
    const activityElement = document.getElementById('playersActivity');
    if (activityElement) {
        activityElement.textContent = randomActivity;
    }
}

// Create mega win effect
function createMegaWin() {
    // Flash effect
    const flash = document.createElement('div');
    flash.style.position = 'fixed';
    flash.style.top = '0';
    flash.style.left = '0';
    flash.style.width = '100%';
    flash.style.height = '100%';
    flash.style.backgroundColor = '#d4af37';
    flash.style.opacity = '0';
    flash.style.pointerEvents = 'none';
    flash.style.zIndex = '9998';
    flash.style.transition = 'opacity 0.2s';
    
    document.body.appendChild(flash);
    
    setTimeout(() => flash.style.opacity = '0.3', 10);
    setTimeout(() => flash.style.opacity = '0', 200);
    setTimeout(() => document.body.removeChild(flash), 400);
    
    // Create special notification
    const winNotifications = document.getElementById('winNotifications');
    if (!winNotifications) return;

    const megaNotification = document.createElement('div');
    megaNotification.className = 'win-notification';
    megaNotification.style.border = '3px solid #d4af37';
    megaNotification.style.background = 'linear-gradient(135deg, #2d2d2d, #1a1a1a)';
    
    megaNotification.innerHTML = `
        <div class="win-header">
            <div class="win-icon">👑</div>
            <div class="win-title" style="color: #d4af37;">MEGA JACKPOT!</div>
        </div>
        <div class="win-details">
            <strong>Anda</strong> memenangkan<br>
            <span class="win-amount" style="color: #d4af37; font-size: 1.3rem;">Rp 50.000.000</span><br>
            di <strong>Lucky Spin</strong>
        </div>
    `;
    
    winNotifications.appendChild(megaNotification);
    
    setTimeout(() => {
        if (megaNotification.parentNode) {
            megaNotification.parentNode.removeChild(megaNotification);
        }
    }, 8000);
}

// Create jackpot reset effect
function createJackpotReset() {
    jackpotAmount = 2524563197; // Reset to base amount
    
    const winNotifications = document.getElementById('winNotifications');
    if (!winNotifications) return;
    
    const resetNotification = document.createElement('div');
    resetNotification.className = 'win-notification';
    resetNotification.style.border = '3px solid #ff6b6b';
    
    resetNotification.innerHTML = `
        <div class="win-header">
            <div class="win-icon">🔄</div>
            <div class="win-title" style="color: #ff6b6b;">JACKPOT RESET!</div>
        </div>
        <div class="win-details">
            Jackpot progresif telah direset<br>
            <span style="color: #ff6b6b;">Bersiaplah untuk putaran baru!</span>
        </div>
    `;
    
    winNotifications.appendChild(resetNotification);
    
    setTimeout(() => {
        if (resetNotification.parentNode) {
            resetNotification.parentNode.removeChild(resetNotification);
        }
    }, 5000);
}

// ======= MAIN WEBSITE FUNCTIONALITY =======
// DOM Ready
document.addEventListener('DOMContentLoaded', function() {
    initializeAll();
});

function initializeAll() {
    headerScroll();
    mobileMenu();
    faqAccordion();
    testimonialCarousel();
    scrollAnimations();
    particlesBackground();
    scrollToTop();
    smoothScrolling();
}

// Header Scroll Effect
function headerScroll() {
    const header = document.getElementById('header');
    let lastScrollY = window.scrollY;

    window.addEventListener('scroll', () => {
        const currentScrollY = window.scrollY;

        if (currentScrollY > 50) {
            header.classList.add('scrolled');
        } else {
            header.classList.remove('scrolled');
        }

        // Hide/show header based on scroll direction
        if (currentScrollY > lastScrollY && currentScrollY > 200) {
            header.style.transform = 'translateY(-100%)';
        } else {
            header.style.transform = 'translateY(0)';
        }

        lastScrollY = currentScrollY;
    });
}

let lastScrollTop = 0;
window.addEventListener('scroll', function() {
    const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
    
    const jackpotProgressive = document.querySelector('.jackpot-countdown');
    if (jackpotProgressive) {
        if (window.innerWidth > 768) {
            if (scrollTop > 200) {
                jackpotProgressive.classList.add('hidden');
            } else {
                jackpotProgressive.classList.remove('hidden');
            }
        } else {
            jackpotProgressive.classList.remove('hidden');
        }
    }
    
    lastScrollTop = scrollTop;
});

// Mobile Menu
function mobileMenu() {
    const mobileMenuBtn = document.getElementById('mobileMenuBtn');
    const navLinks = document.getElementById('navLinks');

    if (!mobileMenuBtn || !navLinks) return;

    mobileMenuBtn.addEventListener('click', () => {
        const isActive = navLinks.classList.contains('active');
        
        navLinks.classList.toggle('active');
        mobileMenuBtn.innerHTML = isActive ? 
            '<i class="fas fa-bars"></i>' : 
            '<i class="fas fa-times"></i>';

        // Prevent body scroll when menu is open
        document.body.style.overflow = isActive ? '' : 'hidden';
    });

    // Close menu when clicking on links
    navLinks.querySelectorAll('a').forEach(link => {
        link.addEventListener('click', () => {
            navLinks.classList.remove('active');
            mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
            document.body.style.overflow = '';
        });
    });

    // Close menu when clicking outside
    document.addEventListener('click', (e) => {
        if (!navLinks.contains(e.target) && !mobileMenuBtn.contains(e.target)) {
            navLinks.classList.remove('active');
            mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
            document.body.style.overflow = '';
        }
    });
}

// FAQ Accordion
function faqAccordion() {
    const faqItems = document.querySelectorAll('.faq-item');

    faqItems.forEach(item => {
        const question = item.querySelector('.faq-question');
        
        if (question) {
            question.addEventListener('click', () => {
                const isActive = item.classList.contains('active');
                
                // Close all items
                faqItems.forEach(faqItem => {
                    faqItem.classList.remove('active');
                });
                
                // Open clicked item if it wasn't active
                if (!isActive) {
                    item.classList.add('active');
                }
            });
        }
    });
}

// Testimonial Carousel
function testimonialCarousel() {
    const track = document.getElementById('testimonialTrack');
    const prevBtn = document.getElementById('prevBtn');
    const nextBtn = document.getElementById('nextBtn');

    if (!track || !prevBtn || !nextBtn) return;

    const slides = track.querySelectorAll('.testimonial-item');
    let currentIndex = 0;
    let autoPlayInterval;

    function goToSlide(index) {
        if (index < 0) {
            index = slides.length - 1;
        } else if (index >= slides.length) {
            index = 0;
        }
        
        currentIndex = index;
        track.style.transform = `translateX(-${currentIndex * 100}%)`;
    }

    function startAutoPlay() {
        autoPlayInterval = setInterval(() => {
            goToSlide(currentIndex + 1);
        }, 5000);
    }

    function stopAutoPlay() {
        clearInterval(autoPlayInterval);
    }

    // Button events
    prevBtn.addEventListener('click', () => {
        stopAutoPlay();
        goToSlide(currentIndex - 1);
        startAutoPlay();
    });

    nextBtn.addEventListener('click', () => {
        stopAutoPlay();
        goToSlide(currentIndex + 1);
        startAutoPlay();
    });

    // Touch/swipe support
    let startX = 0;
    let endX = 0;

    track.addEventListener('touchstart', (e) => {
        startX = e.touches[0].clientX;
        stopAutoPlay();
    });

    track.addEventListener('touchend', (e) => {
        endX = e.changedTouches[0].clientX;
        const diff = startX - endX;
        
        if (Math.abs(diff) > 50) {
            if (diff > 0) {
                goToSlide(currentIndex + 1);
            } else {
                goToSlide(currentIndex - 1);
            }
        }
        startAutoPlay();
    });

    // Pause on hover
    track.addEventListener('mouseenter', stopAutoPlay);
    track.addEventListener('mouseleave', startAutoPlay);

    // Start autoplay
    startAutoPlay();
}

// Scroll Animations
function scrollAnimations() {
    const observerOptions = {
        threshold: 0.1,
        rootMargin: '0px 0px -100px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
                observer.unobserve(entry.target);
            }
        });
    }, observerOptions);

    // Observe all animated elements
    const animatedElements = document.querySelectorAll('.fade-in, .slide-in-left, .slide-in-right, .scale-in');
    animatedElements.forEach(el => {
        observer.observe(el);
    });

    // Initial animation for hero
    setTimeout(() => {
        const heroElements = document.querySelectorAll('.hero .slide-in-left, .hero .slide-in-right');
        heroElements.forEach(el => {
            el.classList.add('visible');
        });
    }, 500);
}

// Particles Background
function particlesBackground() {
    const particlesContainer = document.getElementById('particles');
    if (!particlesContainer) return;

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');

    function resizeCanvas() {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    }

    resizeCanvas();
    canvas.style.cssText = `
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
    `;

    particlesContainer.appendChild(canvas);

    class Particle {
        constructor() {
            this.reset();
            this.y = Math.random() * canvas.height;
            this.opacity = Math.random() * 0.5 + 0.2;
            this.size = Math.random() * 2 + 1;
        }

        reset() {
            this.x = Math.random() * canvas.width;
            this.y = -10;
            this.vx = (Math.random() - 0.5) * 2;
            this.vy = Math.random() * 1 + 0.5;
        }

        update() {
            this.x += this.vx;
            this.y += this.vy;

            if (this.y > canvas.height + 10 || this.x < -10 || this.x > canvas.width + 10) {
                this.reset();
            }
        }

        draw() {
            ctx.save();
            ctx.globalAlpha = this.opacity;
            ctx.beginPath();
            ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
            ctx.fillStyle = '#d4af37';
            ctx.fill();
            ctx.restore();
        }
    }

    const particles = [];
    const particleCount = Math.min(60, Math.floor(canvas.width * canvas.height / 20000));

    for (let i = 0; i < particleCount; i++) {
        particles.push(new Particle());
    }

    function animate() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        particles.forEach((particle, i) => {
            particle.update();
            particle.draw();

            // Connect nearby particles
            for (let j = i + 1; j < particles.length; j++) {
                const dx = particles[i].x - particles[j].x;
                const dy = particles[i].y - particles[j].y;
                const distance = Math.sqrt(dx * dx + dy * dy);

                if (distance < 100) {
                    ctx.save();
                    ctx.globalAlpha = 0.1 * (1 - distance / 100);
                    ctx.beginPath();
                    ctx.strokeStyle = '#d4af37';
                    ctx.lineWidth = 1;
                    ctx.moveTo(particles[i].x, particles[i].y);
                    ctx.lineTo(particles[j].x, particles[j].y);
                    ctx.stroke();
                    ctx.restore();
                }
            }
        });

        requestAnimationFrame(animate);
    }

    animate();

    window.addEventListener('resize', () => {
        resizeCanvas();
        // Adjust particle count
        const newCount = Math.min(60, Math.floor(canvas.width * canvas.height / 20000));
        if (newCount !== particles.length) {
            particles.length = 0;
            for (let i = 0; i < newCount; i++) {
                particles.push(new Particle());
            }
        }
    });
}

// Scroll to Top
function scrollToTop() {
    const scrollTopBtn = document.getElementById('scrollTopBtn');
    if (!scrollTopBtn) return;

    window.addEventListener('scroll', () => {
        if (window.scrollY > 300) {
            scrollTopBtn.classList.add('visible');
        } else {
            scrollTopBtn.classList.remove('visible');
        }
    });

    scrollTopBtn.addEventListener('click', () => {
        window.scrollTo({
            top: 0,
            behavior: 'smooth'
        });
    });
}

// Smooth Scrolling for anchor links
function smoothScrolling() {
    const links = document.querySelectorAll('a[href^="#"]');

    links.forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            
            const targetId = link.getAttribute('href');
            const targetElement = document.querySelector(targetId);
            
            if (targetElement) {
                const headerHeight = document.getElementById('header').offsetHeight;
                const targetPosition = targetElement.offsetTop - headerHeight - 20;
                
                window.scrollTo({
                    top: targetPosition,
                    behavior: 'smooth'
                });
            }
        });
    });
}

// Additional optimizations
function debounce(func, wait) {
    let timeout;
    return function executedFunction(...args) {
        const later = () => {
            clearTimeout(timeout);
            func(...args);
        };
        clearTimeout(timeout);
        timeout = setTimeout(later, wait);
    };
}

// Performance optimizations
window.addEventListener('scroll', debounce(() => {
    // Any scroll-based functions can be added here
}, 10));

// Error handling
window.addEventListener('error', (e) => {
    console.warn('Non-critical error:', e.error);
});

window.addEventListener('unhandledrejection', (e) => {
    console.warn('Promise rejection:', e.reason);
    e.preventDefault();
});

// Preload critical resources
function preloadResources() {
    const link = document.createElement('link');
    link.rel = 'preload';
    link.as = 'font';
    link.href = 'https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap';
    link.crossOrigin = 'anonymous';
    document.head.appendChild(link);
}

// Initialize preloading
preloadResources();

// Lazy loading for images (when added)
function initLazyLoading() {
    const imageObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                const img = entry.target;
                if (img.dataset.src) {
                    img.src = img.dataset.src;
                    img.classList.remove('lazy');
                    imageObserver.unobserve(img);
                }
            }
        });
    });

    // Observe all lazy images
    document.querySelectorAll('img[data-src]').forEach(img => {
        imageObserver.observe(img);
    });
}

// Initialize lazy loading
initLazyLoading();

// Service worker registration (for PWA capabilities)
if ('serviceWorker' in navigator) {
    window.addEventListener('load', () => {
        navigator.serviceWorker.register('/sw.js')
            .then(() => console.log('SW registered'))
            .catch(() => console.log('SW registration failed'));
    });
}

// Accessibility improvements
function initAccessibility() {
    // Focus trap for mobile menu
    const navLinks = document.getElementById('navLinks');
    const firstFocusableElement = navLinks?.querySelector('a');
    const lastFocusableElement = navLinks?.querySelector('a:last-child');

    if (navLinks && firstFocusableElement && lastFocusableElement) {
        navLinks.addEventListener('keydown', (e) => {
            if (e.key === 'Tab') {
                if (e.shiftKey) {
                    if (document.activeElement === firstFocusableElement) {
                        lastFocusableElement.focus();
                        e.preventDefault();
                    }
                } else {
                    if (document.activeElement === lastFocusableElement) {
                        firstFocusableElement.focus();
                        e.preventDefault();
                    }
                }
            }
        });
    }

    // Skip link
    const skipLink = document.createElement('a');
    skipLink.href = '#hero';
    skipLink.textContent = 'Skip to main content';
    skipLink.className = 'skip-link';
    skipLink.style.cssText = `
        position: absolute;
        top: -40px;
        left: 10px;
        background: var(--accent-gold);
        color: var(--dark-bg);
        padding: 8px 16px;
        border-radius: 4px;
        z-index: 10000;
        transition: top 0.3s;
        font-weight: 600;
    `;

    skipLink.addEventListener('focus', function() {
        this.style.top = '10px';
    });

    skipLink.addEventListener('blur', function() {
        this.style.top = '-40px';
    });

    document.body.insertBefore(skipLink, document.body.firstChild);
}

// Initialize accessibility
initAccessibility();

// Analytics placeholder (replace with actual analytics code)
function initAnalytics() {
    // Google Analytics or other analytics initialization
    // gtag('config', 'GA_MEASUREMENT_ID');
}

// Cookie consent (placeholder)
function initCookieConsent() {
    // Cookie consent banner implementation
}

// Initialize additional features
setTimeout(() => {
    initAnalytics();
    initCookieConsent();
}, 1000);

// Keyboard shortcuts for slot
document.addEventListener('keydown', (e) => {
    // Press 'S' to spin
    if (e.key.toLowerCase() === 's' && !e.ctrlKey && !e.altKey && !e.shiftKey) {
        if (document.activeElement.tagName !== 'INPUT' && document.activeElement.tagName !== 'TEXTAREA') {
            manualSpin();
        }
    }
    
    // Press 'Space' to toggle slot
    if (e.key === ' ' && window.innerWidth > 768) {
        if (document.activeElement.tagName !== 'INPUT' && document.activeElement.tagName !== 'TEXTAREA') {
            toggleSlot();
            e.preventDefault();
        }
    }
});

console.log('Idnarena website with floating mini slot loaded successfully!');
console.log('Desktop controls: Drag to move, click to expand/collapse, S to spin, Space to toggle');
console.log('Click outside mini slot to auto-close when expanded');

        console.log('Idnarena website loaded successfully!');
    </script>

    <!-- Schema Markup -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Organization",
      "name": "Idnarena",
      "url": "https://www.idnarena.com",
      "logo": "https://www.idnarena.com/logo.png",
      "description": "Situs judi online terpercaya dengan berbagai pilihan game menarik, bonus melimpah, dan layanan 24 jam.",
      "contactPoint": {
        "@type": "ContactPoint",
        "telephone": "+628123456789",
        "contactType": "customer service",
        "availableLanguage": ["Indonesian", "English"]
      },
      "sameAs": [
        "https://www.facebook.com/idnarena",
        "https://www.twitter.com/idnarena",
        "https://www.instagram.com/idnarena"
      ]
    }
    </script>

    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Bagaimana cara mendaftar di Idnarena?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Proses pendaftaran di Idnarena sangat mudah. Cukup klik tombol 'Daftar Sekarang' di halaman utama, isi formulir dengan data Anda yang valid, lalu verifikasi akun melalui email atau nomor telepon."
          }
        },
        {
          "@type": "Question",
          "name": "Apakah Idnarena aman dan terpercaya?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Ya, Idnarena menggunakan teknologi enkripsi SSL 256-bit dan memiliki lisensi resmi untuk melindungi data pribadi dan transaksi keuangan Anda."
          }
        },
        {
          "@type": "Question",
          "name": "Berapa minimal deposit di Idnarena?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Minimal deposit di Idnarena hanya Rp 10.000 dengan berbagai metode pembayaran termasuk bank lokal, e-wallet, dan pulsa."
          }
        }
      ]
    }