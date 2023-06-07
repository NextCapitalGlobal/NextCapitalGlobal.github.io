<template>
  <Header :lang=lang :langs=langs :menu=menu :email=email :contact_btn=contact_btn />
  <!-- main -->
  <div class="main-container" ref="about">
    <Intro :content=intro />
  </div>
  <div class="card-container text-center clearfix">
    <img class="float-right hidden md:inline-block" src="@/assets/card-yellow.png">
    <img class="float-none inline-block md:float-right" src="@/assets/card-blue.png">
  </div>
  <div class="feature-container">
    <Feature :feature=feature />
  </div>
  <!-- intro -->
  <div class="intro-container">
    <Card :card=card />
  </div>
  <!-- contact -->
  <div class="contact-container" ref="contact">
    <Contact :inquiry=inquiry :subscribe=subscribe :email=email />
  </div>
  <!-- footer -->
  <Footer :menu=menu :email=email :fb=fb />
</template>

<script>
import Header from './components/Header.vue'
import Intro from './components/Intro.vue'
import Feature from './components/Feature.vue'
import Contact from './components/Contact.vue'
import Card from './components/Card.vue'
import Footer from './components/Footer.vue'

function imageUrl(image) {
  return new URL(`./assets/${image}`, import.meta.url).href;
}

export default {
  data() {
    return {
      email: "contact@nextcapital.global",
      fb: "https://www.facebook.com/NextCapitalGlobal/",
      langs: [
        {
          'title': 'English',
          'value': 'en'
        },
        {
          'title': 'Chinese',
          'value': 'ch'
        }
      ],
      lang: 'en',
      menu: [
        {
          'title': 'About Us',
          'value': 'about'
        },
        {
          'title': 'Contact Us',
          'value': 'contact'
        }
      ],
      contact_btn: "Contact us",
      intro: {
        name: "Next Capital",
        title: "Next Capital<br>Driving the Future of <p class='highlight'>Fintech</p>",
        desc: "Next Capital is a venture capital (VC) firm that invests in promising companies related to financial technology (FinTech) to drive the future development of FinTech. The firm’s investments cover a wide range of financial services, including payments, peer-to-peer lending, blockchain services, wealth management, insurance technology, and more."
      },
      feature: {
        title: "Secure and reliable NEXT is here to assist you.",
        list: [
          {
            title: "Having your MasterCard",
            desc: "Next Capital issues MasterCard credit cards.",
            icon: imageUrl("icon-money.svg")
          },
          {
            title: "X Pay offers payment collection and disbursement services.",
            desc: "X Pay offers corporate partnership plans that provide fast payment links and support for crypto payment and collection, allowing merchants to collect crypto payments from consumers.",
            icon: imageUrl("icon-pay.svg")
          },
          {
            title: "Digital Check service - BitCheck.",
            desc: "We provide the safest free online performance bond for your cross-border trade and international payments.",
            icon: imageUrl("icon-grow.svg")
          }
        ]
      },
      news: {
        title: "Latest News:",
        content: [
          {
            "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
            "date": "Event period: 2022-01-22 to 2022-12-30.",
            "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          },
          {
            "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
            "date": "Event period: 2022-01-22 to 2022-12-30.",
            "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          },
          {
            "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
            "date": "Event period: 2022-01-22 to 2022-12-30.",
            "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          }
        ]
      },
      card: {
        title: "Having your <p class='highlight'>MasterCard</p>",
        desc: [
          'New users can enjoy a lower service fee rate when applying.',
          'Under the Next Capital group, users can enjoy additional benefits when using all services.',
        ],
        btn: 'Coming soon'
      },
      inquiry: {
        title: "Interested in Next Capital?",
        intro: "Consult our business specialist now.",
        btn: "Contact us."
      },
      subscribe: {
        title: "Stay updated with our latest news and updates.",
        email_default_msg: "Enter your email address.",
        link: "mailto:contact@nextcapital.global?subject=NextCapital%20subscribe%20the%20latest%20NEWS&body=Hi%20NextCapital%0ASubscribe%20the%20latest%20NEWS%0A%0AThank%20you",
        btn: "Subscribe"
      }
    }
  },
  components: {
    Header,
    Intro,
    Feature,
    Card,
    Contact,
    Footer
  },
  methods: {
    goto(selection) {
      const el = this.$refs[selection];
      var offset = document.getElementById('header').clientHeight;
      var elPosition = el.getBoundingClientRect().top;
      var position = elPosition + window.pageYOffset - offset;

      window.scrollTo({
        top: position,
        behavior: 'smooth'
      });
    }
  }
}
</script>
