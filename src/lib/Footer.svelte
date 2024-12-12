<script lang="ts">
  const currentYear = new Date().getFullYear();
  
  const links = {
    company: [
      { text: 'About', href: '#about' },
      { text: 'Services', href: '#services' },
      { text: 'Portfolio', href: '#portfolio' },
      { text: 'Careers', href: '#careers' }
    ],
    resources: [
      { text: 'Blog', href: '#blog' },
      { text: 'Case Studies', href: '#case-studies' },
      { text: 'Documentation', href: '#docs' },
      { text: 'Support', href: '#support' }
    ],
    legal: [
      { text: 'Privacy Policy', href: '#privacy' },
      { text: 'Terms of Service', href: '#terms' },
      { text: 'Cookie Policy', href: '#cookies' },
      { text: 'GDPR', href: '#gdpr' }
    ]
  };

  const socials = [
    { icon: 'M22 4.01c-1 .49-1.98.689-3 .99-1.121-1.265-2.783-1.335-4.38-.737S11.977 6.323 12 8v1c-3.245.083-6.135-1.395-8-4 0 0-4.182 7.433 4 11-1.872 1.247-3.739 2.088-6 2 3.308 1.803 6.913 2.423 10.034 1.517 3.58-1.04 6.522-3.723 7.651-7.742a13.84 13.84 0 0 0 .497-3.753C20.18 7.773 21.692 5.25 22 4.009z', href: '#twitter' },
    { icon: 'M16 8.049c0-4.446-3.582-8.05-8-8.05C3.58 0-.002 3.603-.002 8.05c0 4.017 2.926 7.347 6.75 7.951v-5.625h-2.03V8.05H6.75V6.275c0-2.017 1.195-3.131 3.022-3.131.876 0 1.791.157 1.791.157v1.98h-1.009c-.993 0-1.303.621-1.303 1.258v1.51h2.218l-.354 2.326H9.25V16c3.824-.604 6.75-3.934 6.75-7.951z', href: '#facebook' },
    { icon: 'M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z', href: '#linkedin' },
    { icon: 'M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z', href: '#github' }
  ];
</script>

<footer class="bg-gray-900 text-white pt-20 pb-6">
  <div class="container">
    <!-- Main Footer Content -->
    <div class="grid md:grid-cols-2 lg:grid-cols-5 gap-12 mb-16">
      <!-- Company Info -->
      <div class="lg:col-span-2">
        <h2 class="text-2xl font-bold mb-6">XYZ</h2>
        <p class="text-gray-400 mb-8 max-w-md">
          Transforming businesses through innovative digital solutions. We help enterprises achieve their digital transformation goals with cutting-edge technology.
        </p>
        <!-- Social Links -->
        <div class="flex space-x-4">
          {#each socials as social}
            <a href={social.href} class="text-gray-400 hover:text-white transition-colors">
              <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                <path d={social.icon}/>
              </svg>
            </a>
          {/each}
        </div>
      </div>

      <!-- Quick Links -->
      <div>
        <h3 class="text-lg font-semibold mb-6">Company</h3>
        <ul class="space-y-4">
          {#each links.company as link}
            <li>
              <a href={link.href} class="text-gray-400 hover:text-white transition-colors">{link.text}</a>
            </li>
          {/each}
        </ul>
      </div>

      <div>
        <h3 class="text-lg font-semibold mb-6">Resources</h3>
        <ul class="space-y-4">
          {#each links.resources as link}
            <li>
              <a href={link.href} class="text-gray-400 hover:text-white transition-colors">{link.text}</a>
            </li>
          {/each}
        </ul>
      </div>

      <div>
        <h3 class="text-lg font-semibold mb-6">Legal</h3>
        <ul class="space-y-4">
          {#each links.legal as link}
            <li>
              <a href={link.href} class="text-gray-400 hover:text-white transition-colors">{link.text}</a>
            </li>
          {/each}
        </ul>
      </div>
    </div>

    <!-- Bottom Bar -->
    <div class="border-t border-gray-800 pt-8">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <p class="text-gray-400 text-sm">
          © {currentYear} XYZ. All rights reserved.
        </p>
        <div class="flex space-x-6 mt-4 md:mt-0">
          <a href="#privacy" class="text-gray-400 hover:text-white text-sm">Privacy Policy</a>
          <a href="#terms" class="text-gray-400 hover:text-white text-sm">Terms of Service</a>
          <a href="#cookies" class="text-gray-400 hover:text-white text-sm">Cookie Policy</a>
        </div>
      </div>
    </div>
  </div>
</footer>