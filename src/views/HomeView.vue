<template>
  <div class="min-h-screen overflow-hidden bg-slate-950 text-white">
    <!-- Background -->
    <div class="absolute inset-0">
      <div
        class="absolute top-0 left-1/2 h-125 w-125 -translate-x-1/2 rounded-full bg-blue-600/20 blur-3xl animate-pulse"
      />
      <div
        class="absolute bottom-0 right-0 h-100 w-100 rounded-full bg-purple-600/20 blur-3xl animate-pulse"
      />
    </div>

    <!-- Hero -->
    <section
      class="relative mx-auto flex min-h-screen max-w-7xl flex-col items-center justify-center px-6 text-center"
    >
      <div
        class="mb-6 rounded-full border border-white/10 bg-white/5 px-4 py-2 text-sm backdrop-blur"
      >
        Building innovative software products
      </div>

      <h1
        class="max-w-5xl text-5xl font-bold leading-tight md:text-8xl"
      >
        Moba Labs
      </h1>

      <p
        class="mt-6 max-w-2xl text-lg text-slate-300 md:text-2xl font-light"
      >
        We design and build modern web applications, mobile apps,
        cloud systems, and AI powered products that help businesses
        move faster.
      </p>

      <div class="mt-10 flex flex-wrap justify-center gap-4">
        <a
          href="#projects"
          class="rounded-xl bg-blue-600 px-6 py-3 font-medium transition hover:scale-105"
        >
          View Projects
        </a>

        <a
          href="#team"
          class="rounded-xl border border-white/10 px-6 py-3 transition hover:bg-white/10"
        >
          Meet the Team
        </a>
      </div>
    </section>

    <!-- Services -->
    <section class="relative py-24">
      <div class="mx-auto max-w-7xl px-6">
        <div class="text-center">
            <span
                class="rounded-full border border-white/10 bg-white/5 px-4 py-2 text-sm text-slate-300"
            >
                What We Do
            </span>
            <h2 class="mt-6 text-4xl font-bold md:text-5xl">
                Building Digital Products That Drive Growth
            </h2>
            <p class="mx-auto mt-4 max-w-2xl text-slate-400">
                We help startups, businesses, and organizations bring ideas to life through
                modern web applications, mobile experiences, cloud infrastructure, and
                AI-powered solutions built for scalability and long-term success.
            </p>
        </div>

        <div class="mt-12 grid gap-6 md:grid-cols-2 lg:grid-cols-4"> 
            <div v-for="service in services" 
                :key="service.title" 
                class="group flex min-h-90 flex-col rounded-3xl border border-white/10 bg-white/5 p-6 backdrop-blur transition-all duration-300 hover:-translate-y-2 hover:border-blue-500/40 hover:bg-white/10" 
            > 
                <div class="mb-5 flex h-14 w-14 items-center justify-center rounded-2xl bg-blue-500/10 text-2xl"> 
                    {{ service.icon }} 
                </div> 
                <h3 class="text-xl font-semibold"> 
                    {{ service.title }} 
                </h3> 
                <p class="mt-3 text-slate-400"> 
                    {{ service.description }} 
                </p> 
                <div class="mt-6 space-y-3"> 
                    <div 
                        v-for="feature in service.features" 
                        :key="feature" 
                        class="flex items-center gap-2 text-sm text-slate-300" 
                    > 
                        <span class="h-2 w-2 rounded-full bg-blue-400" /> 
                        {{ feature }} 
                    </div> 
                </div> 
                <div class="mt-auto pt-6"> 
                    <span 
                        class="inline-flex rounded-full border border-white/10 px-3 py-1 text-xs text-slate-400" 
                    > 
                        End-to-End Delivery 
                    </span> 
                </div> 
            </div> 
        </div>      
      </div>
    </section>

    <!-- Projects -->
    <section
      id="projects"
      class="relative py-24"
    >
      <div class="mx-auto max-w-7xl px-6">
        <div class="text-center">
            <span
                class="rounded-full border border-white/10 bg-white/5 px-4 py-2 text-sm text-slate-300"
            >
                Ongoing Projects
            </span>
            <h2 class="mt-6 text-4xl font-bold md:text-5xl">
                Turning Ambitious Ideas Into Real Products
            </h2>
            <p class="mx-auto mt-4 max-w-2xl text-slate-400">
                Every project at Moba Labs begins with a bold vision and a commitment to
                excellence. We transform emerging ideas into scalable products designed to
                create lasting impact for people and communities.
            </p>
        </div>

        <div class="mt-12 grid gap-6 md:grid-cols-2">
          <div
            v-for="project in projects"
            :key="project.name"
            class="rounded-3xl border border-white/10 bg-white/5 p-8 backdrop-blur transition hover:border-blue-500/40"
          >
            <span
              class="rounded-full bg-blue-500/20 px-3 py-1 text-sm text-blue-300"
            >
              {{ project.status }}
            </span>

            <h3 class="mt-4 text-2xl font-bold">
              {{ project.name }}
            </h3>

            <p class="mt-4 text-slate-400">
              {{ project.description }}
            </p>

            <div class="mt-6 flex flex-wrap gap-2">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="rounded-full border border-white/10 px-3 py-1 text-xs text-slate-300"
              >
                {{ tag }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Team -->
    <section class="py-28" id="team">
        <div class="mx-auto max-w-7xl px-6">
            <div class="text-center">
                <span
                    class="rounded-full border border-white/10 bg-white/5 px-4 py-2 text-sm text-slate-300"
                >
                    Meet The Team
                </span>

                <h2 class="mt-6 text-4xl font-bold md:text-5xl">
                    The People Behind Moba Labs
                </h2>

                <p class="mx-auto mt-4 max-w-2xl text-slate-400">
                    Passionate builders creating innovative products,
                    digital experiences and technology solutions.
                </p>
            </div>

            <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3 mt-6">
                <!-- Team Members -->
                <div
                    v-for="member in teamMembers"
                    :key="member.name"
                    class="group rounded-3xl border border-white/10 bg-white/5 p-6 backdrop-blur transition hover:-translate-y-2 hover:bg-white/10"
                >
                    <img
                        :src="member.image || '/team/fallback.png'"
                        :alt="member.name"
                        class="mx-auto h-28 w-28 rounded-full object-cover"
                    />

                    <h3 class="mt-5 text-center text-xl font-semibold">
                        {{ member.name }}
                    </h3>

                    <p class="text-center text-blue-300">
                        {{ member.role }}
                    </p>

                    <p class="mt-4 text-center text-slate-400">
                        {{ member.bio }}
                    </p>

                    <a
                        v-if="member.linkedIn"
                        :href="member.linkedIn"
                        target="_blank"
                        class="mt-6 flex items-center justify-center gap-2 text-sm text-slate-300 transition hover:text-blue-300"
                    >
                        LinkedIn →
                    </a>
                </div>

                <!-- Join Us Card -->
                <div
                    class="group flex min-h-90 flex-col items-center justify-center rounded-3xl border border-dashed border-white/20 bg-white/5 p-8 text-center transition hover:border-blue-500/40 hover:bg-white/10"
                >
                    <div
                        class="mb-4 flex h-20 w-20 items-center justify-center rounded-full bg-white/10 text-4xl"
                    >
                        +
                    </div>

                    <h3 class="text-2xl font-semibold">
                        Join Us
                    </h3>

                    <p class="mt-3 text-slate-400">
                        We are always interested in connecting with developers,
                        designers and innovators.
                    </p>

                    <a
                        href="https://linkedin.com/company/moba-labs"
                        target="_blank"
                        class="mt-6 rounded-xl bg-blue-600 px-5 py-3 transition hover:scale-105"
                    >
                        Connect on LinkedIn
                    </a>
                </div>

            </div>
        </div>
    </section>
  </div>
</template>

<script setup lang="ts">
const teamMembers = [
    {
        name: "Ayobami Ajibola",
        image: "/team/ayo.png",
        role: "Lead Software Engineer",
        bio: `Building scalable web applications, mobile products,
      cloud systems and AI powered solutions.`,
        linkedIn: "https://www.linkedin.com/in/ayobamiajibola"
    },
    {
        name: "David Ojoniyi",
        image: "/team/david.jpeg",
        role: "Product Designer",
        bio: `Designing intuitive digital experiences that balance user needs, 
        business goals, and innovative technology to create impactful products.`,
        linkedIn: "https://www.linkedin.com/in/davidaustin9"
    },
    {
        name: "Emmanuel Onmeje",
        image: "",
        role: "Intern",
        bio: `Aspiring software developer passionate about building modern 
        web and mobile applications while continuously learning new technologies 
        and best practices.`,
        linkedIn: ""
    }
]

const services = [ 
    { 
        icon: '🌐', 
        title: 'Web Applications', 
        description: `Modern websites, customer portals, SaaS platforms 
        and internal business systems built for performance and scale.`, 
        features: [ 
            'Custom Web Platforms', 
            'SaaS Products', 
            'Admin Dashboards', 
            'E-Commerce Solutions' 
        ] 
    }, 
    { 
        icon: '📱', 
        title: 'Mobile Development', 
        description: `Cross-platform mobile applications that deliver seamless 
        experiences across Android and iOS devices.`, 
        features: [ 
            'React Native Apps', 
            'iOS & Android', 
            'Push Notifications', 
            'Offline Support' 
        ] 
    }, 
    { 
        icon: '☁️', 
        title: 'Cloud Infrastructure', 
        description: `Scalable backend systems, APIs, databases and cloud 
        infrastructure designed for reliability and growth.`, 
        features: [ 
            'REST APIs', 
            'PostgreSQL & MongoDB', 
            'Docker & Kubernetes', 
            'CI/CD Automation' 
        ] 
    },   
    { 
        icon: '🤖', 
        title: 'AI Solutions', 
        description: `Intelligent applications powered by machine learning, 
        automation and modern AI technologies.`, 
        features: [ 
            'AI Assistants', 
            'LLM Integration', 
            'Workflow Automation', 
            'Predictive Analytics' 
        ] 
    } 
]

const projects = [
    {
      name: 'StressShield',
      status: 'Research & Development',
      description:
        `A wellness platform that leverages machine learning and personal wellness data 
        to provide personalized insights, identify stress patterns, and help users 
        build healthier habits through proactive recommendations.`,
      // tags: ['Python', 'ML', 'Analytics']
    },
    {
        name: 'TalkSharp',
        status: 'Active Development',
        description:
        `A language learning platform focused on preserving and promoting 
        African languages through interactive lessons, cultural context, 
        personalized learning paths, and AI-powered conversational practice.`,
        // tags: ['React', 'React-Native', 'Firebase', 'AI', 'NestJS']
    },
    {
        name: 'Game On',
        status: 'Active Development',
        description:
        `A community-driven sports platform that helps people discover, 
        create, and join local games and activities. From basketball and 
        soccer to recreational meetups, Game On makes it easy to connect, 
        compete, and stay active.`,
        // tags: ['React', 'React-Native', 'Firebase', 'AI', 'NestJS']
    }
]
</script>