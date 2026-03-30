<template>
  <section class="max-w-[1440px] mx-auto px-12 mb-40 pt-20">
    <div class="grid grid-cols-12 gap-12">
      <!-- Profile Sidebar -->
      <div class="col-span-12 md:col-span-4 sticky top-40 h-fit">
        <div class="aspect-square bg-surface-dim overflow-hidden grayscale hover:grayscale-0 transition-all duration-700">
          <img 
            src="../../assets/profile.png" 
            alt="Gabriel Osmin Hernandez Cruz" 
            class="w-full h-full object-cover"
            onerror="this.style.display='none'; this.parentNode.innerHTML='<div class=\'w-full h-full bg-outline-variant flex items-center justify-center text-secondary font-bold font-headline uppercase tracking-widest text-[0.6875rem]\'>No Photo</div>'"
          />
        </div>
        <div class="mt-12 flex flex-col gap-6">
          <div v-for="item in contactInfo" :key="item.label">
            <span class="font-label text-[0.625rem] tracking-widest uppercase text-secondary/60">{{ item.label }}</span>
            <p class="font-headline font-bold text-[0.6875rem] uppercase text-primary mt-1">{{ item.value }}</p>
          </div>
        </div>
      </div>

      <!-- Main Biographical Content -->
      <div class="col-span-12 md:col-span-8 flex flex-col gap-32">
        <!-- Biography -->
        <div>
          <h2 class="text-display-lg text-primary uppercase mb-6">PERFIL</h2>
          <h3 class="text-3xl font-black uppercase text-secondary/30 tracking-tight mb-12">ESPECIALISTA FRONTEND</h3>
          <div class="text-body-lg text-on-surface leading-loose max-w-2xl font-medium space-y-8">
            <p>
              Soy <strong>desarrollador Frontend</strong>, trabajando principalmente con <strong>Vue</strong> y <strong>WordPress</strong>. Tengo experiencia en HTML, CSS, JavaScript y Python, y me gusta crear sitios web modernos, rápidos y bien optimizados, cuidando tanto el rendimiento como los detalles.
            </p>
            <p>
              Actualmente estoy formándome en un curso de desarrollo <strong>Fullstack</strong>, ampliando mis conocimientos para tener una visión más completa y aportar aún más valor en los proyectos en los que participo.
            </p>
            <p>
              Me apasiona la tecnología y todo lo que implica construir cosas útiles y atractivas en la web. Siempre estoy aprendiendo, probando nuevas herramientas y buscando mejorar en cada reto.
            </p>
            <p>
              A nivel personal, me considero alguien creativo, con <strong>ideas diferentes</strong> (a veces un poco loca), pero siempre enfocadas en aportar algo nuevo. Me adapto rápido a los cambios, disfruto salir de mi zona de confort y encontrar soluciones incluso en situaciones poco convencionales.
            </p>
          </div>
        </div>

        <!-- Education -->
        <div>
          <h2 class="text-display-sm text-primary uppercase mb-12 flex items-center gap-4">
            FORMACIÓN ACADÉMICA
            <span class="h-[1px] flex-grow bg-outline-variant"></span>
          </h2>
          <div class="flex flex-col gap-16">
            <div v-for="edu in education" :key="edu.title" class="grid grid-cols-8 gap-8 group">
              <div class="col-span-2">
                <span class="font-label text-[0.6875rem] tracking-widest text-secondary group-hover:text-primary transition-colors">{{ edu.period }}</span>
              </div>
              <div class="col-span-6">
                <h3 class="font-headline font-bold text-xl uppercase text-primary mb-2">{{ edu.title }}</h3>
                <p class="font-label text-[0.6875rem] tracking-widest text-secondary uppercase mb-2">{{ edu.institution }}</p>
                <p class="text-body-md text-on-surface/60">{{ edu.location }}</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Cursos Lanbide (NEW SECTION) -->
        <div>
          <h2 class="text-display-sm text-primary uppercase mb-12 flex items-center gap-4">
            CURSOS DE ESPECIALIZACIÓN
            <span class="h-[1px] flex-grow bg-outline-variant"></span>
          </h2>
          <div class="flex flex-col gap-10">
            <div v-for="course in lanbideCourses" :key="course.id" class="border-b border-outline-variant/30 pb-8 last:border-0 group">
              <h3 class="font-headline font-bold text-lg uppercase text-primary mb-1 group-hover:text-primary-fixed transition-colors">
                {{ course.title }}
              </h3>
              <p class="font-label text-[0.625rem] tracking-widest text-secondary/60 uppercase">
                LANBIDE — ID: {{ course.id }}
              </p>
            </div>
          </div>
        </div>

        <!-- Experience -->
        <div>
          <h2 class="text-display-sm text-primary uppercase mb-12 flex items-center gap-4">
            EXPERIENCIA PROFESIONAL
            <span class="h-[1px] flex-grow bg-outline-variant"></span>
          </h2>
          <div class="flex flex-col gap-12">
            <div v-for="exp in experience" :key="exp.id" class="grid grid-cols-8 gap-8 group border-b border-outline-variant/30 pb-12 last:border-0 last:pb-0">
              <div class="col-span-2">
                <span class="font-label text-[0.6875rem] tracking-widest text-secondary group-hover:text-primary transition-colors">{{ exp.period }}</span>
              </div>
              <div class="col-span-6">
                <h3 class="font-headline font-bold text-xl uppercase text-primary mb-2 line-clamp-2">{{ exp.title }}</h3>
                <p class="font-label text-[0.6875rem] tracking-widest text-secondary uppercase mb-4">{{ exp.company }} — {{ exp.location }}</p>
                <p class="text-body-md text-on-surface/80 leading-relaxed max-w-xl">
                  {{ exp.description }}
                </p>
              </div>
            </div>
          </div>
        </div>

        <!-- Idiomas -->
        <div>
          <h2 class="text-display-sm text-primary uppercase mb-8">IDIOMAS</h2>
          <ul class="flex gap-20">
            <li>
              <span class="font-label text-[0.625rem] tracking-widest uppercase text-secondary">CASTELLANO</span>
              <p class="font-headline font-bold text-[0.6875rem] uppercase text-primary mt-1">Nativo</p>
            </li>
            <li>
              <span class="font-label text-[0.625rem] tracking-widest uppercase text-secondary">INGLÉS</span>
              <p class="font-headline font-bold text-[0.6875rem] uppercase text-primary mt-1">Básico Intermedio</p>
            </li>
          </ul>
        </div>

        <!-- Philosophy -->
        <div class="pt-20 border-t border-outline-variant/30">
          <span class="font-label text-[0.625rem] tracking-[0.3em] uppercase text-secondary/60 mb-12 block">FILOSOFÍA</span>
          <div class="grid grid-cols-2 gap-16 mb-32">
            <div>
              <h3 class="text-2xl font-black uppercase tracking-tighter mb-6">
                LA OBJETIVIDAD ES LA <span class="text-[#c00]">VERDAD.</span>
              </h3>
              <p class="text-secondary leading-relaxed font-medium">
                Eliminamos el ego del diseñador para dejar que la información hable. Mi metodología se basa en la cuadrícula no como una caja, sino como un esqueleto. Si la estructura es sólida, el contenido se vuelve ligero.
              </p>
            </div>
            <div>
              <h3 class="text-2xl font-black uppercase tracking-tighter mb-6">
                LA REDUCCIÓN COMO <span class="text-[#c00]">VALOR.</span>
              </h3>
              <p class="text-secondary leading-relaxed font-medium">
                La simplicidad es el resultado de un intenso trabajo intelectual. Restar es clarificar. Cada elemento debe justificar su existencia a través de su utilidad o necesidad estructural.
              </p>
            </div>
          </div>

          <!-- Contact Black Box with CV Download -->
          <div class="bg-primary p-20 text-center text-white relative group overflow-hidden">
            <h2 class="text-[clamp(1.5rem,4vw,3.5rem)] font-black leading-tight uppercase tracking-tighter mb-12 transition-all">
              ¿LISTO PARA ESTABLECER TU<br/>ARCHIVO DIGITAL?
            </h2>
            <div class="flex flex-col sm:flex-row justify-center gap-6">
              <a 
                href="#contact" 
                class="inline-block bg-[#c00] text-white px-10 py-5 font-headline font-bold text-[0.6875rem] uppercase tracking-widest hover:bg-[#a00] hover:scale-105 transition-all duration-300"
              >
                SOLICITAR COLABORACIÓN
              </a>
              <a 
                href="/cv-gabriel-hernandez.pdf" 
                download
                class="inline-block border border-white/30 text-white px-10 py-5 font-headline font-bold text-[0.6875rem] uppercase tracking-widest hover:bg-white hover:text-primary hover:scale-105 transition-all duration-300"
              >
                DESCARGAR CV (PDF)
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const contactInfo = [
  { label: 'E-MAIL', value: 'hernandezcruz.gabrielosmin@gmail.com' },
  { label: 'DISPONIBILIDAD', value: 'Bilbao, España' },
  { label: 'TELÉFONO', value: '+34 610 41 7752' }
]

const education = [
  {
    period: '2025 — ACTUALIDAD',
    title: 'Bootcamp FullStack (8 MESES)',
    institution: 'Lanbide, Peñascal F5',
    location: 'Bilbao, España'
  },
  {
    period: '2019 — 2020 (2 AÑOS)',
    title: 'Técnico en Computación',
    institution: 'Universidad Dr. Andrés Bello',
    location: 'Sonsonate, El Salvador'
  },
  {
    period: '2016 — 2018 (3 AÑOS)',
    title: 'Bachillerato Técnico Vocacional En Desarrollo De Software',
    institution: 'Instituto Nacional De Acajutla',
    location: 'Sonsonate, El Salvador'
  }
]

const lanbideCourses = [
  { id: '24483360', title: 'IFCD0040OH - HERRAMIENTAS WEB 3.0. APLICACIÓN EN TU EMPRESA' },
  { id: '24483354', title: 'IFCD022PO - DESARROLLO WEB PARA COMERCIO ELECTRÓNICO' },
  { id: '24483358', title: 'IFCI0068OH - USABILIDAD WEB' }
]

const experience = [
  {
    id: 1,
    period: 'OCT 2025 — ACTUALIDAD',
    title: 'Programador Full Stack',
    company: 'Peñascal F5',
    location: 'BOLUETA, PAÍS VASCO, ESPAÑA',
    description: 'Trabajando en el desarrollo de soluciones integrales con un enfoque moderno y colaborativo.'
  },
  {
    id: 2,
    period: '2021 — 2024',
    title: 'Restoration Technician',
    company: 'First To Respond Restoration',
    location: 'RESEDA, LOS ÁNGELES CA, EE.UU.',
    description: 'Restauración por daños de fuego, remediación de moho, limpieza de humo y hollín, y servicios de daños por agua.'
  }
]
</script>
