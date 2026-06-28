import '@/styles/globals.css'
import '@/styles/navbar.css'
import '@/styles/portfolio.css'
import '@/styles/home.css'
import '@/styles/media.css'
import Script from 'next/script'
import Layout from './components/Layout'
import AOS from 'aos'
import 'aos/dist/aos.css'
import { useEffect } from 'react'

export default function App({ Component, pageProps }) {
  useEffect(() => {
    AOS.init({
      once: true,       // animate only once, not every scroll
      duration: 800,    // optional, tune to your preference
    })
  }, [])

  return (
    `<>`
      `<Layout>`
        `<Component {...pageProps} />`
      `</Layout>`
      `<Script`
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js"`
        `integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4"`
        `crossOrigin="anonymous"`
        `strategy="afterInteractive"`
      `/>`
    `</>`
  )
}