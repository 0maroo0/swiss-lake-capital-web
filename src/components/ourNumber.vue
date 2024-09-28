<template>
  <div class="our-number">
    <div class="card-container">
      <div class="card" v-for="client in clients" :key="client.id">
        <img src="../assets/happyClint.png" alt="Image" class="card-image" />
        <h3 class="card-title">{{ client.title }}</h3>
        <p class="client-number">{{ animatedCount }}</p>
        <button class="contact-button">
          Our Percent: {{ client.percent }}%
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      clients: [
        {
          id: 1,
          title: "Happy Client 1",
          number: 100,
          image: "../assets/happyClint.png",
          percent: 17,
        },
        {
          id: 2,
          title: "Happy Client 2",
          number: 200,
          image: "../assets/percentAward.png",
          percent: 25,
        },
        {
          id: 1,
          title: "Happy Client 1",
          number: 100,
          image: "../assets/happyClint.png",
          percent: 17,
        },
        {
          id: 2,
          title: "Happy Client 2",
          number: 200,
          image: "../assets/percentAward.png",
          percent: 25,
        },
      ],
      animatedCount: 0,
      animationDuration: 2000, // Animation duration in milliseconds
    };
  },
  methods: {
    animateNumber(targetNumber) {
      const startTime = performance.now(); // Get the current time
      const startNumber = 1; // Start from 1
      const endNumber = targetNumber; // Target number

      const animate = (currentTime) => {
        const elapsedTime = currentTime - startTime; // Calculate elapsed time
        const progress = Math.min(elapsedTime / this.animationDuration, 1); // Normalize progress
        this.animatedCount = Math.floor(
          startNumber + (endNumber - startNumber) * progress
        ); // Update count

        if (progress < 1) {
          requestAnimationFrame(animate); // Request next animation frame
        }
      };

      requestAnimationFrame(animate); // Start the animation
    },
  },
  mounted() {
    // Start animation for each client when component is mounted
    this.clients.forEach((client) => {
      this.animateNumber(client.number);
    });
  },
};
</script>

<style>
.contact-button {
  all: unset;
  width: 100px;
  height: 30px;
  font-size: 16px;
  background: transparent;
  align-items: center;
  align-content: center;
  border: none;
  position: relative;
  color: #f0f0f0;
  cursor: pointer;
  z-index: 1;
  padding: 10px 20px;
  margin: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  white-space: nowrap;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.contact-button::after,
.contact-button::before {
  content: "";
  position: absolute;
  bottom: 0;
  right: 0;
  z-index: -99999;
  transition: all 0.4s;
}

.contact-button::before {
  transform: translate(0%, 0%);
  width: 100%;
  height: 100%;
  background: #2947a9;
  border-radius: 10px;
}

.contact-button::after {
  transform: translate(10px, 10px);
  width: 35px;
  height: 35px;
  background: #ffffff15;
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  border-radius: 50px;
}

.contact-button:hover::before {
  transform: translate(5%, 20%);
  width: 110%;
  height: 110%;
}

.contact-button:hover::after {
  border-radius: 10px;
  transform: translate(0, 0);
  width: 100%;
  height: 100%;
}

.contact-button:active::after {
  transition: 0s;
  transform: translate(0, 5%);
}
.our-number {
  display: flex;
}
.our-number {
  display: flex;
  flex-direction: row; /* جعل المحتوى عمودي */
  align-items: center; /* محاذاة المحتوى في المنتصف */
}

.company-info {
  align-items: center;
  align-content: center;
  text-align: center; /* محاذاة النص في المنتصف */
  margin-bottom: 20px; /* هامش أسفل القسم */
}
p {
  font-weight: bold;
  font-size: 30px;
}
.card-container {
  margin-top: 40px;
  background-color: white;
  margin: 30px;
  display: flex; /* استخدام flexbox */
  flex-wrap: wrap; /* السماح للبطاقات بالالتفاف */
  justify-content: center; /* مركزية العناصر */
  gap: 80px; /* المسافة بين البطاقات */
  padding: 20px; /* تباعد حول الحاوية */
}

.card {
  position: relative; /* ضبط الموضع النسبي للبطاقة */
  background-color: #fff; /* خلفية بيضاء للبطاقة */
  border-radius: 10px; /* زوايا دائرية */
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1); /* ظل خفيف */
  padding: 20px; /* تباعد داخلي */
  text-align: center; /* محاذاة النص في المنتصف */
  width: 200px; /* عرض ثابت للبطاقات */
  margin: 10px; /* تباعد خارجي */
}

.card-image {
  position: absolute; /* ضبط الصورة بشكل مطلق */
  top: -40px; /* رفع الصورة للأعلى */
  right: -40px; /* دفع الصورة لليمين */
  width: 80px; /* عرض ثابت للصورة */
  height: auto; /* الحفاظ على نسبة العرض إلى الارتفاع */
  border-radius: 10px; /* زوايا دائرية للصورة */
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); /* ظل خفيف للصورة */
}

.card-title {
  font-size: 1.5em; /* حجم خط أكبر للعنوان */
  color: #333; /* لون داكن للعنوان */
  margin-bottom: 10px; /* مسافة أسفل العنوان */
}

.client-number {
  font-size: 2.5em; /* حجم خط أكبر للرقم */
  color: #007bff; /* لون رئيسي */
  margin: 10px 0; /* مسافة أعلى وأسفل */
}

.percentage-button {
  background-color: #28a745; /* خلفية خضراء للزر */
  color: white; /* نص أبيض */
  border: none; /* لا حدود */
  border-radius: 5px; /* زوايا دائرية للزر */
  padding: 10px 20px; /* تباعد داخلي */
  font-size: 1em; /* حجم خط الزر */
  cursor: pointer; /* مؤشر زر */
  transition: background-color 0.3s; /* تغيير الخلفية بسلاسة */
}

.percentage-button:hover {
  background-color: #218838; /* أخضر داكن عند التمرير */
}
</style>
