<!DOCTYPE html>
<html lang="en" data-bs-theme="light">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>SocialApp — Home</title>

  <!-- Bootstrap 5.3 CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
  <!-- Bootstrap Icons -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css" rel="stylesheet">

  <style>
    /* Page tweaks */
    body { background: var(--bs-body-bg); }
    .navbar .form-control:focus { box-shadow: none; }
    .story-avatar {
      width: 60px; height: 60px; border-radius: 50%;
      border: 2px solid var(--bs-primary); object-fit: cover;
    }
    .composer textarea { resize: none; }
    .feed-card img { max-height: 420px; object-fit: cover; }
    .btn-icon { border: none; background: transparent; padding: .25rem .5rem; }
    .btn-icon:focus { outline: none; box-shadow: none; }
    .suggestion-avatar, .friend-avatar {
      width: 36px; height: 36px; border-radius: 50%; object-fit: cover;
    }
    .online-dot {
      width: 10px; height: 10px; border-radius: 50%;
      background: #22c55e; border: 2px solid var(--bs-body-bg);
      position: absolute; bottom: 0; right: 0;
    }
    .sticky-sidebar { position: sticky; top: 76px; }
    .card-flat { border: 1px solid var(--bs-border-color); }
    .text-muted-small { font-size: .9rem; color: var(--bs-secondary-color); }

    /* Mobile adjustments */
    @media (max-width: 991.98px) {
      .sticky-sidebar { position: static; top: auto; }
    }
  </style>
</head>
<body>

  <!-- ===== Header / Navbar ===== -->
  <nav class="navbar navbar-expand-lg bg-body-tertiary border-bottom sticky-top">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">
        <i class="bi bi-share-fill text-primary"></i>
        <strong>SocialApp</strong>
      </a>
    </div>
        

      <!-- Search -->
      <form class="d-none d-md-flex ms-3 flex-grow-1" role="search" style="max-width: 560px;">
        <div class="input-group">
          <span class="input-group-text bg-light border-end-0"><i class="bi bi-search"></i></span>
          <input class="form-control border-start-0" type="search" placeholder="Search people, posts, or tags…" aria-label="Search">
        </div>
      </form>

      <div class="d-flex align-items-center ms-auto gap-2">
        <!-- Theme toggle -->
        <button class="btn btn-outline-secondary" id="themeToggle" type="button" aria-label="Toggle dark mode">
          <i class="bi bi-moon"></i>
        </button>

        <!-- Create -->
        <button class="btn btn-primary d-none d-sm-inline-flex" data-bs-toggle="modal" data-bs-target="#createModal">
          <i class="bi bi-plus-lg me-1"></i> Create
        </button>

        <!-- Notifications -->
        <button class="btn btn-light position-relative" type="button" aria-label="Notifications">
          <i class="bi bi-bell fs-5"></i>
          <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">3</span>
        </button>

        <!-- Messages -->
        <button class="btn btn-light" type="button" aria-label="Messages">
          <i class="bi bi-chat-dots fs-5"></i>
        </button>

        <!-- Profile Dropdown -->
        <div class="dropdown">
          <button class="btn btn-light d-flex align-items-center gap-2 dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
            <img src="https://ui-avatars.com/api/?name=Teja&background=0D8ABC&color=fff" alt="Profile" width="28" height="28" class="rounded-circle">
ton>
          <ul class="dropdown-menu dropdown-menu-end">
            <li>#<i class="bi bi-person me-2"></i> Profile</a></li>
            <li><ai class="bi bi-gear me-2"></i> Settings</a></li>
            <li><hr class="dropdown-divider"></li>
            <li>#<i class="bi bi-box-arrow-right me-2"></i> Logout</a></li>
          </ul>
        </div>

        <!-- Mobile toggler -->
        <button class="navbar-toggler ms-2" type="button" data-bs-toggle="offcanvas" data-bs-target="#mobileNav" aria-controls="mobileNav" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
      </div>
    </div>
  </nav>

  <!-- Offcanvas Mobile Menu -->
  <div class="offcanvas offcanvas-end" tabindex="-1" id="mobileNav" aria-labelledby="mobileNavLabel">
    <div class="offcanvas-header">
      <h5 class="offcanvas-title" id="mobileNavLabel">Menu</h5>
      <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
    </div>
    <div class="offcanvas-body d-flex flex-column gap-3">
      <form role="search">
        <div class="input-group">
          <span class="input-group-text bg-light border-end-0"><i class="bi bi-search"></i></span>
          <input class="form-control border-start-0" type="search" placeholder="Search…">
        </div>
      </form>
      <ul class="nav flex-column">
        <li class="nav-item">#<i class="bi bi-house me-2"></i> Home</a></li>
        <li class="nav-item"><a class="nav-link"mpass me-2"></i> Explore</a></li>
        <li class="nav-item"><a class=""bi bi-collection-play me-2"></i> Reels</a></li>
        <li class="nav-item">#<i class="bi bi-bookmark me-2"></i> Saved</a></li>
        <li class="nav-item"><a class="nav-link" hrefme-2"></i> Friends</a></li>
      </ul>
      <div class="d-grid gap-2 mt-3">
        <button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#createModal"><i class="bi bi-plus-lg me-1"></i> Create Post</button>
        <button class="btn btn-outline-secondary" id="themeToggleMobile"><i class="bi bi-moon me-1"></i> Toggle Theme</button>
      </div>
    </div>
  </div>

  <!-- ===== Main Content ===== -->
  <main class="container py-4">
    <div class="row g-4">

      <!-- Center column -->
      <div class="col-12 col-lg-8 col-xl-7">

        <!-- Stories -->
        <div class="card card-flat">
          <div class="card-body">
            <div class="d-flex align-items-center justify-content-between mb-3">
              <h6 class="mb-0">Stories</h6>
              <button class="btn btn-sm btn-outline-primary"><i class="bi bi-plus-lg me-1"></i>Add Story</button>
            </div>
            <div class="d-flex flex-nowrap gap-3 overflow-auto pb-2">
              <!-- Example story items -->
              <div class="text-center">
                https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=400
                <div class="small mt-2">Aisha</div>
              </div>
              <div class="text-center">
                https://images.unsplash.com/photo-1531123897727-8f129e1688ce?q=80&w=400
                <div class="small mt-2">Karan</div>
              </div>
              <div class="text-center">
                <img class="story-avatar" src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w="small mt-2">Mina</div>
              </div>
              <div class="text-center">
                https://images.unsplash.com/photo-1527980965255-d3b416303d12?q=80&w=400
                <div class="small mt-2">Leo</div>
              </div>
              <div class="text-center">
                <img class="story-avatar" src="https://images.unsplash.com/photo-1527980965255-d3b416303d12?q=80&w=400" altt-2">Sara</div>
              </div>
            </div>
          </div>
        </div>

        <!-- Composer -->
        <div class="card card-flat mt-3 composer">
          <div class="card-body">
            <div class="d-flex align-items-start gap-3">
              <img src="https://ui-avatars.com/api/?name=Teja&background=0D8ABC&color=fff" alt="You" width="44" height="44" class       <textarea class="form-control mb-2" rows="3" placeholder="What's happening, Teja?"></textarea>
                <div class="d-flex flex-wrap gap-2 justify-content-between">
                  <div class="d-flex flex-wrap gap-2">
                    <button class="btn btn-light btn-sm"><i class="bi bi-image me-1"></i> Photo</button>
                    <button class="btn btn-light btn-sm"><i class="bi bi-camera-video me-1"></i> Video</button>
                    <button class="btn btn-light btn-sm"><i class="bi bi-emoji-smile me-1"></i> Feeling</button>
                    <button class="btn btn-light btn-sm"><i class="bi bi-geo-alt me-1"></i> Check-in</button>
                  </div>
                  <button class="btn btn-primary btn-sm"><i class="bi bi-send me-1"></i> Post</button>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Feed (Example Posts) -->
        <article class="card card-flat mt-3 feed-card">
          <div class="card-header bg-transparent d-flex align-items-center justify-content-between">
            <div class="d-flex align-items-center gap-2">
              <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=80" alt="Aisha"              <div class="fw-semibold">Aisha Khan</div>
                <div class="text-muted-small">2 hours ago · Hyderabad</div>
              </div>
            </div>
            <button class="btn btn-sm btn-light"><i class="bi bi-three-dots"></i></button>
          </div>
          <div class="card-body">
            <p>Weekend vibes at Tank Bund 🌅 #Hyderabad #Sunset</p>
            <img class="w-100 rounded" src="https://images.unsplash.com/photo-1519681393784-d120267933ba?q=80&w=1200" alt="Post image">
bg-transparent">
            <div class="d-flex align-items-center gap-3">
              <button class="btn-icon text-danger like-btn"><i class="bi bi-heart"></i> <span class="like-count">24</span></button>
              <button class="btn-icon"><i class="bi bi-chat"></i> 6</button>
              <button class="btn-icon"><i class="bi bi-reply"></i> Share</button>
              <span class="ms-auto text-muted-small"><i class="bi bi-eye me-1"></i> 1.2k views</span>
            </div>
          </div>
        </article>

        <article class="card card-flat mt-3 feed-card">
          <div class="card-header bg-transparent d-flex align-items-center justify-content-between">
            <div class="d-flex align-items-center gap-2">
              <img src="https://images.unsplash.com/photo-1531123897727-8f129e1688ce?q=80&w=80" alt="Karan" class="rounded-circless="fw-semibold">Karan Verma</div>
                <div class="text-muted-small">5 hours ago · Bengaluru</div>
              </div>
            </div>
            <button class="btn btn-sm btn-light"><i class="bi bi-three-dots"></i></button>
          </div>
          <div class="card-body">
            <p>Shipped v2 of our app 🚀 Loving the new UI!</p>
            <img class="w-100 rounded" src="https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=1200" alts="card-footer bg-transparent">
            <div class="d-flex align-items-center gap-3">
              <button class="btn-icon text-danger like-btn"><i class="bi bi-heart"></i> <span class="like-count">58</span></button>
              <button class="btn-icon"><i class="bi bi-chat"></i> 12</button>
              <button class="btn-icon"><i class="bi bi-reply"></i> Share</button>
              <span class="ms-auto text-muted-small"><i class="bi bi-eye me-1"></i> 3.9k views</span>
            </div>
          </div>
        </article>

        <!-- Load more -->
        <div class="d-grid mt-4">
          <button class="btn btn-outline-primary">Load more</button>
        </div>
      </div>

      <!-- Right sidebar -->
      <aside class="col-12 col-lg-4 col-xl-5">
        <div class="sticky-sidebar">

          <!-- Suggestions -->
          <div class="card card-flat">
            <div class="card-header bg-transparent">
              <h6 class="mb-0">Suggested for you</h6>
            </div>
            <ul class="list-group list-group-flush">
              <li class="list-group-item d-flex align-items-center justify-content-between">
                <div class="d-flex align-items-center gap-2">
                  <img class="suggestion-avatar" src="https://images.unsplash.com/photo-150700321          <div>
                    <div class="fw-semibold">Mina Patel</div>
                    <div class="text-muted-small">@minapatel</div>
                  </div>
                </div>
                <button class="btn btn-sm btn-outline-primary">Follow</button>
              </li>
              <li class="list-group-item d-flex align-items-center justify-content-between">
                <div class="d-flex align-items-center gap-2">
                  https://images.unsplash.com/photo-1527980965255-d3b416303d12?q=80&w=80
                  <div>
                    <div class="fw-semibold">Leo Kumar</div>
                    <div class="text-muted-small">@leok</div>
                  </div>
                </div>
                <button class="btn btn-sm btn-outline-primary">Follow</button>
              </li>
              <li class="list-group-item d-flex align-items-center justify-content-between">
                <div class="d-flex align-items-center gap-2">
                  <img class="suggestion-avatar" src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=80" alt="Aishav class="fw-semibold">Aisha Khan</div>
                    <div class="text-muted-small">@aishakhan</div>
                  </div>
                </div>
                <button class="btn btn-sm btn-outline-primary">Follow</button>
              </li>
            </ul>
          </div>

          <!-- Trending -->
          <div class="card card-flat mt-3">
            <div class="card-header bg-transparent">
              <h6 class="mb-0">Trending tags</h6>
            </div>
            <div class="card-body">
              <div class="d-flex flex-wrap gap-2">
                ##Hyderabad</a>
                ##Tech</a>
                <a href="#" class="badge text-bg-info text-decoration-none">#Photography</a>

              </div>
            </div>
          </div>

          <!-- Online friends -->
          <div class="card card-flat mt-3">
            <div class="card-header bg-transparent">
              <h6 class="mb-0">Online friends</h6>
            </div>
            <div class="list-group list-group-flush">
              <div class="list-group-item d-flex align-items-center gap-2">
                <div class="position-relative">
                  <img class="friend-avatar" src="https://images.unsplash.com/photo-1531123897727-8f129e1688ce?q=80&w=80" alte-dot"></span>
                </div>
                <div>
                  <div class="fw-semibold">Karan Verma</div>
                  <div class="text-muted-small">Active now</div>
                </div>
                <button class="btn btn-sm btn-outline-secondary ms-auto"><i class="bi bi-chat-dots me-1"></i> Message</button>
              </div>
              <div class="list-group-item d-flex align-items-center gap-2">
                <div class="position-relative">
                  https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=80
                  <span class="online-dot"></span>
                </div>
                <div>
                  <div class="fw-semibold">Mina Patel</div>
                  <div class="text-muted-small">Online</div>
                </div>
                <button class="btn btn-sm btn-outline-secondary ms-auto"><i class="bi bi-chat-dots me-1"></i> Message</button>
              </div>
              <div class="list-group-item d-flex align-items-center gap-2">
                <div class="position-relative">
                  <img class="friend-avatar" src="https://images.unsplash.com/photo-1527980965255-d3b416303d12?q class="online-dot"></span>
                </div>
                <div>
                  <div class="fw-semibold">Leo Kumar</div>
                  <div class="text-muted-small">Online</div>
                </div>
                <button class="btn btn-sm btn-outline-secondary ms-auto"><i class="bi bi-chat-dots me-1"></i> Message</button>
              </div>
            </div>
          </div>

        </div>
      </aside>

    </div>
  </main>

  <!-- ===== Create Post Modal ===== -->
  <div class="modal fade" id="createModal" tabindex="-1" aria-labelledby="createModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="createModalLabel">Create a post</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <textarea class="form-control" rows="4" placeholder="Share something with your friends…"></textarea>
          <div class="d-flex flex-wrap gap-2 mt-3">
            <button class="btn btn-light btn-sm"><i class="bi bi-image me-1"></i> Photo</button>
            <button class="btn btn-light btn-sm"><i class="bi bi-camera-video me-1"></i> Video</button>
            <button class="btn btn-light btn-sm"><i class="bi bi-emoji-smile me-1"></i> Feeling</button>
            <button class="btn btn-light btn-sm"><i class="bi bi-geo-alt me-1"></i> Check-in</button>
          </div>
        </div>
        <div class="modal-footer">
          <button class="btn btn-outline-secondary" data-bs-dismiss="modal">Cancel</button>
          <button class="btn btn-primary"><i class="bi bi-send me-1"></i> Post</button>
        </div>
      </div>
    </div>
  </div>

  <!-- Bootstrap JS (includes Popper) -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/jsndle.min.js</script>

  <!-- Minimal interactivity -->
  <script>
    // Theme toggle
    (function () {
      const root = document.documentElement;
      const get = () => localStorage.getItem('theme') || 'light';
      const set = (t) => { localStorage.setItem('theme', t); root.setAttribute('data-bs-theme', t); };
      set(get());
      function toggle() { set(get() === 'light' ? 'dark' : 'light'); }
      document.getElementById('themeToggle')?.addEventListener('click', toggle);
      document.getElementById('themeToggleMobile')?.addEventListener('click', toggle);
    })();

    // Like button demo (toggles count)
    document.querySelectorAll('.like-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        const icon = btn.querySelector('i');
        const countEl = btn.querySelector('.like-count');
        const count = parseInt(countEl.textContent, 10);
        const liked = icon.classList.toggle('bi-heart-fill');
        icon.classList.toggle('bi-heart', !liked);
        countEl.textContent = liked ? count + 1 : Math.max(0, count - 1);
      });
    });
  </script>
</body>
</html>
