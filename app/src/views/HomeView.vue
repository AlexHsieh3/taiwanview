<script setup lang="ts">
import { ref } from 'vue'

// 四大特色
const features = ref([
  {
    icon: 'schedule',
    title: '準時出發',
    description: '嚴格控管時間，行程不延誤。我們重視您的每一分每一秒，確保旅途順暢。',
    bgColor: 'bg-sky-50',
    iconColor: 'text-sky-500'
  },
  {
    icon: 'airline_seat_recline_extra',
    title: '專業駕駛',
    description: '駕駛團隊經驗豐富，定期培訓。熟悉全台路況，給您最平穩舒適的乘車體驗。',
    bgColor: 'bg-amber-50',
    iconColor: 'text-amber-500'
  },
  {
    icon: 'handshake',
    title: '誠信服務',
    description: '價格透明公開，絕無隱形消費。服務實在，建立長久信任的合作關係。',
    bgColor: 'bg-teal-50',
    iconColor: 'text-teal-500'
  },
  {
    icon: 'security',
    title: '安全至上',
    description: '定期車輛保養與安檢，行車有保障。全車系配備高規格安全設施，讓您安心出遊。',
    bgColor: 'bg-red-50',
    iconColor: 'text-red-500'
  }
])

// 車隊資訊
const fleets = ref([
  {
    id: 1,
    name: '豪華大型遊覽車',
    seats: '43 人座',
    feature: '超大行李空間',
    description: '寬敞舒適的三排座椅設計，適合公司團體旅遊、學校校外教學、進香團體。',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAglvOsumi84o7UmI-yW2CAOKOfIsH4e7l6IOHutdXr11-XJsoq65TS0QT6CiG7G2m126tbhUUx9zYRLdzg3JL76mM9BzO29R1CK23vUU214jJcra5ryTqGVYeiPAXR-8YnNigvFiZvg6qt0VBLqSMO9v8t8rZFAINxuhnlbvqRcU0YnjJU7is2nqrYYrB90g2N7s1PcPFCHK9InBu3_HjlHm3qHxLG-otOX5kmgI0ntG1ornt_5AQOapEueqqwn-nx69s9Z5z6Cs3S',
    badge: '熱門首選',
    badgeColor: 'bg-sky-500',
    amenities: ['wifi', 'mic', 'tv', 'ac_unit'],
    amenityLabels: ['WiFi 熱點', '卡拉OK', '數位電視', '冷暖空調']
  },
  {
    id: 2,
    name: '精緻中型巴士',
    seats: '20-25 人座',
    feature: '機動性高',
    description: '靈活穿梭山林小徑，適合家族旅遊、小型聚會、深度旅遊行程。',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDZQ5MmcJRJcK2N9N31Uu5CoU4TNUwDg2Ojj2tt-Hvzz5P8FWcRNtW2_PU43PiTn5M6vXzj-FoRSDIsj9l7aAi-z4fLUi6e4mZARUU7IkjNIMgzhmtrMIWySAlEQNuxPcQzqC34gPn0_oEkSjLwvZ10Vu02OdyEBY7PkpnBeEbBT1hoTo8uL4RyLuruiuuqAmin-iOzGPYx2Eq-fhdQzH9IFS_YbgCriiByNpMRXgaHWWn23JyerpOQ-9gblNRYiFT79OcCq6ZGWE5V',
    badge: null,
    amenities: ['music_note', 'battery_charging_full', 'chair', 'local_drink'],
    amenityLabels: ['音響設備', 'USB充電', '舒適座椅', '瓶裝水']
  },
  {
    id: 3,
    name: '頂級保姆車 (VIP)',
    seats: '9 人座',
    feature: '總裁級享受',
    description: '極致奢華的移動空間，適合商務接待、明星保姆車、高端私人行程。',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuB2Ee0jaGv_yvVLLZd4AnYKbNfdLZIFSAMzUp1VQl1aBg9Ck70ePWNmiHEQtVvXurdJQ8BEu00WNuzMtDi0upwym2QoSZgTtZH-ewHiZ6X8xyddX-pT7nY3d7SjySDFZplAYAVdUUeT1S-Y7JlKsXwnaZAh7nwjidUihWTmM6DQsThRvLosDc44JtgIk2f98eqOYMvTltNr1yuSf-oA7Il5WkS3nXplq4OuFMiqN8YTD6lXkj0eWvyk69o5Y5qrpXDyzB1IEnDmm8PF',
    badge: 'VIP 尊榮',
    badgeColor: 'bg-amber-400 text-slate-900',
    amenities: ['weekend', 'table_restaurant', 'wine_bar', 'curtains'],
    amenityLabels: ['按摩座椅', '辦公桌', '迷你吧', '隱私窗簾']
  }
])

// 服務項目
const services = ref([
  {
    icon: 'landscape',
    label: '環島旅遊',
    title: '深度旅遊規劃',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuC9Pc7AWI5_rrMz00eBZMadWznNYuoZnqWChYbNDfdEywbd2e6GzJUqlPTKiBZwiy9iwMWcx1jn51MO8oY6cvq6arToIg0OQzjjiYPjKuiL0p3JjkY6i__jO0NW27G0HNbHIwBBdD9A0KN93YXhnnKrVsDO6Y9JXUsegztIzea3ywus0G0n-NXFsyAoAguCQ52onhocIFqHaf-3pV_jw43ocPSsqrpaDsfHDsNBLwMqXKRfm4Yz5mX0Z8RV4M2JDgifQq-yCk2dPfJF',
    span: ''
  },
  {
    icon: 'flight_takeoff',
    label: '機場接送',
    title: '桃園/松山機場接送',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDUdOGXV3eDKhKMj5inzqJxefAqOSshJU_20_CNsFpLAeKED3-Qj7jH_Uq0NeSmKjtle-kf9_O-Lujn49VWr0EDKZr61I3ccuDR7Qi66-mYCK7yq2df3jx3XjiwFOqZarLPCJTius7Zaxgn9qon9YK4nclu6eEeJf6nHSw0LxYtAx7vTtHSIjSOxANguiCI2k1Am9-nvfw2xKANvRdgE0jaM-E-SwFgxs-18Uor4KB47RNcuPujgosXbg_vY8cWVhgZWZNrBNQvQrR9',
    span: ''
  },
  {
    icon: 'business_center',
    label: '企業服務',
    title: '商務考察與通勤',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCiGtTp3Xsixdx910KGVtn-H8nSqVBVTKnm6Hh6ZdJyhzmVJgDdcp8xY_IX00sPu5Lro3fvMZgQ-hiypqsLx5smP-4akVxAE_w1XRXXCbNiVKtDDxcCydEU9SxaD6vJRGWc1s95cuJgeAp26fvG7mJxg_Wzg8wvjZKzcGtLcJDsF_8ouYJQkL9uzGShhTvZ7D_t3GNN30ZEfOCZUWVTOzB2MfVZGGmxfRWGRL3VjpTXmTy6fKT_0ZDPqWVzg5uv5s5eYB85mb8MAdku',
    span: ''
  },
  {
    icon: 'favorite',
    label: '喜慶宴客',
    title: '婚喪喜慶包車',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAd0ScR7KtlyZMAUSQMR5kfqxBEhBgTxZI1FCnRe-wqaXCWzh_V8vqqpmIzr3wIR6TnfI7yN1RvuuCz5jFYhPOQTWRbdTu8i94OIumUHEmHEuPBa5ee2K-njHZ3D58RNyu-mqixjaK4MMkGnZAGYGHvPONK13nXH-fHpKZaUjyooZFxyFUZ-BXi9fxEt7VT6BpqSxXq7Qi-ZJ_gHTNbBh0fQQCIqyHtXoFQ8pbxh8vmc8jnPKxI6uHdHJiYGumII8CYxF8e7O_AaBdT',
    span: ''
  },
  {
    icon: 'school',
    label: '學校團體',
    title: '校外教學與畢業旅行',
    image: 'https://lh3.googleusercontent.com/aida-public/AB6AXuC0Fpt0KuGVCTXSMXo-gAiyJosXFyr6OMBRwuTA4ODm5R8KU1nL4brVnnQwipxgLDMBjPdRrjXtXo16_7MOb5T37uPQBNQalQsZmDVFIitiqI5LyoqSrniIgg_VskTGAyc1Uj4LeY2hdirFUip4TlohJ7Gp2mlAraLAU_WfpcVdmWFLLblUYxYlOog7k3je08UhECezqFYyRB0fhwreK_HIgtWRCeQrFHFaUoxgMcOfXEpbI15iLXF0Fu0Y54Pz-2qK2dflotOzKm3D',
    span: 'lg:col-span-2'
  }
])

// 客戶評價
const testimonials = ref([
  {
    name: '陳小姐',
    title: '科技公司 HR',
    content: '這次公司員工旅遊選擇了大視界的服務，司機大哥非常專業且親切，車內環境整潔舒適，讓我們有一趟非常愉快的旅程！',
    avatar: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAdZcslFaC2AirIQBbahvVYeGgKxIUMvzrBJmYsloSNP7fF91qn4n_6-q0KEyzVZibfWOhEOctq_GFPPCVOTKgt_EWVwBDMkI4-xFLQLp1bghUwJ6U5lGZnAcKwqgQJ06a63jmzEjdgKygVILzQ2aTshg44TSdDNIkPuLVKg8rZZ9eaFvFL4VLEMoV3oU2fFmHTHjehrzITKBIwLStLyXfgsUp5VFtaljcPTwtNHGppybmbdeJuHripIfcIf2XUgDe99zXa0kknQZkW'
  },
  {
    name: '林先生',
    title: '家庭旅遊',
    content: '非常推薦！準時是最基本的，但大視界做到了超越期待的服務。車子很新，長輩們都坐得很舒服，下次家族旅遊一定再找你們。',
    avatar: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCvxdSNL2Ah49wRzm1ZeunGLsiuK5RGacfJHkrU9tAOLRDdFiEfwwwt9ZV9dksT7jXECoTbFAs7QXIhMWouShFFuyJTb-erDS_aPZfuq3i-c8NGI0qMf6425IFQmwcZ-wgSk8BB4q8kY5Pndf2lNAfyIAGQSWefhH6C8bmV4DywBzucyYulstH_3K2zTmXDP1W39v5ukzvesuANZ82SV9WYHveco-fEQoZ_-aho7NIGZSI4fPM3uz8b-PkmPEZ45L2261G7079tJmSW'
  },
  {
    name: '張老師',
    title: '高中導師',
    content: '我們是學校畢業旅行，感謝大視界配合度高，行程安排也很順暢，讓學生們留下了美好的回憶。',
    avatar: 'https://lh3.googleusercontent.com/aida-public/AB6AXuD3tGMoVYb04NoC_hUC0eq1-UPDK3Begbu_oXwZ9jcMXBRLozR15XD8gU65KF4FkTd0Q18IUuytdWfiT4Lsjon0hT_B0Wf5kiJ0T46dVPALboG-1qKupW6oJsLwZ5Ee4Je003pwqHJPPBOFSgONW58FGdOOGxyU65ZNHnNSRwjzGdsAivZUV3-509LVH8fcg53qAkhT6GZSojqqwfa7T7oAiJPM0GB4p_BGT6iydcNF7XdAg31HsdX5_SJNyQTCjj31nH7Z3h3h_hrf'
  }
])

// 表單資料
const contactForm = ref({
  name: '',
  phone: '',
  date: '',
  busType: '',
  message: ''
})

const handleSubmit = () => {
  console.log('表單提交:', contactForm.value)
  alert('感謝您的詢問！我們會盡快與您聯繫。')
  contactForm.value = { name: '', phone: '', date: '', busType: '', message: '' }
}
</script>

<template>
  <div>
    <!-- Hero Section -->
    <section class="relative min-h-[90vh] flex items-center justify-center overflow-hidden">
      <!-- Background Image -->
      <div class="absolute inset-0 z-0">
        <img
          src="https://lh3.googleusercontent.com/aida-public/AB6AXuCwqqblk6Ff61p2OTvWSD_Sm10i2uksKxzpjDlfcWRRZij-Ihjtjsi-zmgc7TX9CF7D34nUDpuBrFWkPbHA7jSFkrJPB7h9h5zXkadVqsU7FOo4vpwEyX-vlM2iFBBkSCVet0dkc3CEJ7cGEVwF5A1IOwOruyxOq14djSbQbTnAR31RB-GLv1HgREYBhjRbhHR_8c9xLMKAUXGAb_juHAzluFEYdzTewxBp1fIU-4z31WqCYtB60JyKfCuvANPXyinNB0qqTTK_ZNQp"
          alt="Beautiful Taiwan landscape"
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-gradient-to-r from-slate-900/60 to-slate-900/30"></div>
      </div>

      <!-- Content -->
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-white">
        <div class="animate-fade-in-up space-y-6">
          <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-sm border border-white/20 mb-4">
            <span class="w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
            <span class="text-sm font-medium tracking-wide">台灣最優質的包車旅遊首選</span>
          </div>

          <h1 class="text-5xl md:text-7xl font-black tracking-tight leading-tight text-shadow">
            準時、專業<br />
            <span class="text-sky-300">誠信</span>、<span class="text-amber-400">安全</span>
          </h1>

          <p class="text-lg md:text-xl text-slate-100 max-w-2xl mx-auto font-light leading-relaxed">
            帶您看見台灣的美，享受舒適安心的旅程。無論是家族旅遊、公司行號包車，大視界都是您最值得信賴的夥伴。
          </p>

          <div class="flex flex-col sm:flex-row gap-4 justify-center mt-8">
            <a href="#contact" class="bg-sky-500 hover:bg-sky-600 text-white text-lg font-bold py-4 px-8 rounded-full shadow-xl transition-all transform hover:-translate-y-1 flex items-center justify-center gap-2">
              開始規劃行程
              <span class="material-symbols-outlined">arrow_forward</span>
            </a>
            <a href="#fleet" class="bg-white hover:bg-slate-100 text-slate-900 text-lg font-bold py-4 px-8 rounded-full shadow-lg transition-all flex items-center justify-center gap-2">
              <span class="material-symbols-outlined">directions_bus</span>
              查看車型
            </a>
          </div>
        </div>
      </div>

      <!-- Wave Bottom -->
      <div class="absolute bottom-0 left-0 right-0">
        <svg class="fill-slate-50 w-full h-16 md:h-24" viewBox="0 0 1440 320" preserveAspectRatio="none">
          <path d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,112C672,96,768,96,864,112C960,128,1056,160,1152,160C1248,160,1344,128,1392,112L1440,96L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path>
        </svg>
      </div>
    </section>

    <!-- Features Section -->
    <section id="about" class="py-20 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-amber-500 font-bold tracking-wider text-sm uppercase mb-2">為什麼選擇大視界</h2>
          <h3 class="text-3xl md:text-4xl font-bold text-slate-900">四大堅持，用心服務</h3>
          <div class="w-20 h-1 bg-sky-500 mx-auto mt-4 rounded-full"></div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div
            v-for="feature in features"
            :key="feature.title"
            class="bg-white p-8 rounded-2xl shadow-sm hover:shadow-xl transition-shadow duration-300 border border-slate-100 group"
          >
            <div :class="[feature.bgColor, feature.iconColor, 'w-14 h-14 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300']">
              <span class="material-symbols-outlined text-4xl">{{ feature.icon }}</span>
            </div>
            <h4 class="text-xl font-bold text-slate-900 mb-3">{{ feature.title }}</h4>
            <p class="text-slate-500 leading-relaxed">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Fleet Section -->
    <section id="fleet" class="py-20 bg-white overflow-hidden">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-end mb-12 gap-6">
          <div>
            <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">豪華車隊展示</h2>
            <p class="text-slate-500 max-w-xl">
              我們提供多種車型選擇，滿足不同團體人數與需求。每輛車皆保持最佳狀態，清潔舒適。
            </p>
          </div>
        </div>

        <!-- Fleet Cards -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="fleet in fleets"
            :key="fleet.id"
            class="bg-white rounded-2xl overflow-hidden shadow-lg border border-slate-100 group"
          >
            <div class="relative h-60 overflow-hidden">
              <img
                :src="fleet.image"
                :alt="fleet.name"
                class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div
                v-if="fleet.badge"
                :class="[fleet.badgeColor || 'bg-sky-500', 'absolute top-4 right-4 text-white text-xs font-bold px-3 py-1 rounded-full shadow-md']"
              >
                {{ fleet.badge }}
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold text-slate-900 mb-2">{{ fleet.name }}</h3>
              <div class="flex items-center gap-2 text-slate-500 text-sm mb-4">
                <span class="material-symbols-outlined text-lg">group</span>
                <span>{{ fleet.seats }}</span>
                <span class="w-1 h-1 bg-slate-300 rounded-full mx-1"></span>
                <span class="material-symbols-outlined text-lg">luggage</span>
                <span>{{ fleet.feature }}</span>
              </div>
              <p class="text-slate-500 text-sm mb-6 line-clamp-2">{{ fleet.description }}</p>
              <div class="grid grid-cols-2 gap-2 mb-6">
                <div
                  v-for="(amenity, index) in fleet.amenities"
                  :key="amenity"
                  class="flex items-center gap-2 text-xs text-slate-600 bg-slate-50 p-2 rounded"
                >
                  <span class="material-symbols-outlined text-sky-500 text-sm">{{ amenity }}</span>
                  {{ fleet.amenityLabels[index] }}
                </div>
              </div>
              <button class="w-full py-3 rounded-xl border border-sky-500 text-sky-500 font-bold hover:bg-sky-500 hover:text-white transition-colors">
                查看詳情
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 bg-sky-50/50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900">全方位旅遊服務</h2>
          <p class="mt-4 text-slate-500">無論您想去哪裡，大視界都能為您安排最合適的交通方案</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="service in services"
            :key="service.title"
            :class="[service.span, 'relative h-64 rounded-2xl overflow-hidden group cursor-pointer shadow-md']"
          >
            <img
              :src="service.image"
              :alt="service.title"
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
            />
            <div class="absolute inset-0 bg-slate-900/40 group-hover:bg-slate-900/50 transition-colors"></div>
            <div class="absolute bottom-0 left-0 p-6 w-full">
              <div class="flex items-center gap-2 text-amber-400 mb-2">
                <span class="material-symbols-outlined">{{ service.icon }}</span>
                <span class="text-sm font-bold uppercase tracking-wider">{{ service.label }}</span>
              </div>
              <h3 class="text-white text-2xl font-bold">{{ service.title }}</h3>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-3xl font-bold text-center text-slate-900 mb-12">客戶好評推薦</h2>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div
            v-for="testimonial in testimonials"
            :key="testimonial.name"
            class="bg-slate-50 p-8 rounded-2xl border border-slate-100"
          >
            <div class="flex items-center gap-1 text-amber-400 mb-4">
              <span v-for="i in 5" :key="i" class="material-symbols-outlined text-sm">star</span>
            </div>
            <p class="text-slate-600 mb-6 italic">"{{ testimonial.content }}"</p>
            <div class="flex items-center gap-4">
              <div class="w-10 h-10 rounded-full bg-slate-300 overflow-hidden">
                <img :src="testimonial.avatar" :alt="testimonial.name" class="w-full h-full object-cover" />
              </div>
              <div>
                <p class="font-bold text-slate-900 text-sm">{{ testimonial.name }}</p>
                <p class="text-slate-400 text-xs">{{ testimonial.title }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-sky-900 text-white relative overflow-hidden">
      <!-- Decorative backgrounds -->
      <div class="absolute top-0 right-0 -mr-20 -mt-20 w-96 h-96 bg-sky-500/20 rounded-full blur-3xl"></div>
      <div class="absolute bottom-0 left-0 -ml-20 -mb-20 w-72 h-72 bg-amber-400/10 rounded-full blur-3xl"></div>

      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <!-- Contact Info -->
          <div>
            <h2 class="text-3xl md:text-4xl font-bold mb-6">立即預約您的旅程</h2>
            <p class="text-sky-200 mb-8 text-lg">填寫下方表單，我們將盡快與您聯繫。或透過電話直接詢問行程報價。</p>

            <div class="space-y-6 mb-10">
              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center shrink-0">
                  <span class="material-symbols-outlined text-amber-400">location_on</span>
                </div>
                <div>
                  <h4 class="font-bold text-lg">公司地址</h4>
                  <p class="text-sky-100">台北市中山區松江路133巷50號3F-4</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center shrink-0">
                  <span class="material-symbols-outlined text-amber-400">call</span>
                </div>
                <div>
                  <h4 class="font-bold text-lg">聯絡電話</h4>
                  <p class="text-sky-100">電話: 02-2954-8100</p>
                  <p class="text-sky-100">手機: 0919-906-715</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-white/10 flex items-center justify-center shrink-0">
                  <span class="material-symbols-outlined text-amber-400">mail</span>
                </div>
                <div>
                  <h4 class="font-bold text-lg">電子郵件</h4>
                  <p class="text-sky-100">fanny5066@yahoo.com.tw</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Contact Form -->
          <div class="bg-white rounded-2xl p-8 shadow-2xl text-slate-900">
            <form @submit.prevent="handleSubmit" class="space-y-4">
              <div class="grid grid-cols-2 gap-4">
                <div>
                  <label class="block text-sm font-medium text-slate-700 mb-1">聯絡人姓名</label>
                  <input
                    v-model="contactForm.name"
                    type="text"
                    placeholder="王小明"
                    class="w-full rounded-lg border-slate-300 focus:border-sky-500 focus:ring focus:ring-sky-500/20 px-4 py-2 border"
                    required
                  />
                </div>
                <div>
                  <label class="block text-sm font-medium text-slate-700 mb-1">聯絡電話</label>
                  <input
                    v-model="contactForm.phone"
                    type="tel"
                    placeholder="0912-345-678"
                    class="w-full rounded-lg border-slate-300 focus:border-sky-500 focus:ring focus:ring-sky-500/20 px-4 py-2 border"
                    required
                  />
                </div>
              </div>

              <div>
                <label class="block text-sm font-medium text-slate-700 mb-1">預計出發日期</label>
                <input
                  v-model="contactForm.date"
                  type="date"
                  class="w-full rounded-lg border-slate-300 focus:border-sky-500 focus:ring focus:ring-sky-500/20 px-4 py-2 border"
                  required
                />
              </div>

              <div>
                <label class="block text-sm font-medium text-slate-700 mb-1">人數/車型需求</label>
                <select
                  v-model="contactForm.busType"
                  class="w-full rounded-lg border-slate-300 focus:border-sky-500 focus:ring focus:ring-sky-500/20 px-4 py-2 border"
                  required
                >
                  <option value="">請選擇...</option>
                  <option value="large">大型遊覽車 (43座)</option>
                  <option value="medium">中型巴士 (20-25座)</option>
                  <option value="vip">九人座/保姆車</option>
                </select>
              </div>

              <div>
                <label class="block text-sm font-medium text-slate-700 mb-1">留言/行程備註</label>
                <textarea
                  v-model="contactForm.message"
                  rows="4"
                  placeholder="請簡述您的旅遊需求或行程規劃..."
                  class="w-full rounded-lg border-slate-300 focus:border-sky-500 focus:ring focus:ring-sky-500/20 px-4 py-2 border"
                ></textarea>
              </div>

              <button
                type="submit"
                class="w-full bg-sky-500 hover:bg-sky-600 text-white font-bold py-3 rounded-lg shadow-lg transition-colors"
              >
                送出詢問
              </button>
            </form>
          </div>
        </div>

        <!-- Map Placeholder -->
        <div class="mt-16 rounded-2xl overflow-hidden shadow-lg h-[300px] border-4 border-white/20">
          <div class="w-full h-full bg-slate-200 relative">
            <img
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuDHL4-h698DSsd7LGJ5G9-_gxdWcFLGUHaFmAOfG6QYkPWbpmzPn9Nw7tjrzx_KC16osmuZFtor-zMRJwxxyoif0sh1lby-L0Ya-G_hDEnGhON7dFRACSJeDESPetzbHc53ypgFQ7M8vO0VcoLs0pNwt9YgNuzdHwJN152d6yIgWms80DS-gaklWm6OffPp2N4GNhNOwGlwmmg-rR2ymD7QnXqDdSku2YIbY9gQAScr3lG29Ab70CKJwvDEHOab-L0c1mI0rs_kmDe2"
              alt="Map location"
              class="w-full h-full object-cover opacity-80"
            />
            <div class="absolute inset-0 flex items-center justify-center">
              <div class="bg-white/90 backdrop-blur px-6 py-3 rounded-lg shadow-xl text-slate-900 font-bold flex flex-col items-center">
                <span class="material-symbols-outlined text-red-500 text-3xl mb-1">location_on</span>
                <span>Google Map Location</span>
                <span class="text-xs font-normal text-slate-500">台北市中山區松江路133巷50號</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
