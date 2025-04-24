import React, { useState } from 'react'; import './fonts.css';

function App() { const [dark, setDark] = useState(false); const [showWelcome, setShowWelcome] = useState(true); const toggleDark = () => setDark(!dark);

const books = [ { title: 'كتاب العادات السبع للناس الأكثر فاعلية', description: 'دليل عملي لتحسين الذات وتطوير الفاعلية الشخصية والمهنية. يناقش الكتاب العادات التي تجعل الأشخاص ناجحين في حياتهم وعلاقاتهم.', file: 'sandbox:/mnt/data/كتاب%20العادات%20السبع%20PDF%20(arab-books.com).pdf' }, { title: 'مغامرات فلفول (75 قصة للأطفال)', description: 'مجموعة قصصية تعليمية وترفيهية للأطفال يتعلم فيها فلفول دروسًا قيمة في كل مغامرة، بلغة بسيطة وسرد ممتع.', file: 'sandbox:/mnt/data/كتاب_مغامرات_فلفول_75صفحة.docx' }, { title: 'كيف تقرأ الناس كأنك تقرأ كتابًا', description: 'كتاب في فنون لغة الجسد وتحليل الشخصيات، يساعدك على فهم سلوك الآخرين والتفاعل معهم بذكاء وفعالية.', file: 'sandbox:/mnt/data/DFRE26G4REG4RE5G7RFG (1).pdf' } ];

if (showWelcome) { return ( <div className={dark ? 'bg-gray-900 text-white min-h-screen p-6 flex flex-col items-center justify-center' : 'bg-white text-black min-h-screen p-6 flex flex-col items-center justify-center'}> <button onClick={toggleDark} className="fixed top-4 left-4 px-4 py-2 bg-gray-700 text-white rounded-lg font-sans">الوضع الداكن</button> <h1 className="text-4xl font-naskh mb-6">مرحباً بك في مكتبة البصائر الرقمية</h1> <p className="mb-4 font-sans text-lg text-center max-w-xl"> مكتبة البصائر الرقمية: منصتك العربية لقراءة وتحميل الكتب والقصص التربوية والمعرفية. واجهة أنيقة، دعم الوضع الليلي، تسجيل دخول سريع، وكتب تناسب جميع الأعمار. المعرفة للجميع، والبصيرة تبدأ من هنا. </p> <div className="space-x-4 rtl:space-x-reverse mb-6"> <button className="bg-blue-700 text-white px-4 py-2 rounded-xl">تسجيل الدخول عبر فيسبوك</button> <button className="bg-red-600 text-white px-4 py-2 rounded-xl">تسجيل الدخول عبر جوجل</button> </div> <button onClick={() => setShowWelcome(false)} className="bg-green-600 text-white px-6 py-2 rounded-xl font-sans mt-4">ادخل إلى المكتبة</button> </div> ); }

return ( <div className={dark ? 'bg-gray-900 text-white min-h-screen p-6' : 'bg-white text-black min-h-screen p-6'}> <button onClick={toggleDark} className="fixed top-4 left-4 px-4 py-2 bg-gray-700 text-white rounded-lg font-sans">الوضع الداكن</button> <h1 className="text-3xl font-bold text-center mb-10 font-naskh">مكتبة البصائر الرقمية</h1>

<div className="space-y-6">
    {books.map((book, i) => (
      <div key={i} className="border rounded-2xl p-6 shadow-md bg-gray-50 dark:bg-gray-800 font-sans">
        <h2 className="text-xl font-semibold mb-2 font-serif">{book.title}</h2>
        <p className="mb-4 font-sans">{book.description}</p>
        <div className="space-x-3 rtl:space-x-reverse">
          <a href={book.file} target="_blank" rel="noopener noreferrer">
            <button className="bg-blue-600 text-white px-4 py-2 rounded-xl font-sans">تحميل</button>
          </a>
          <a href={book.file} target="_blank" rel="noopener noreferrer">
            <button className="bg-green-600 text-white px-4 py-2 rounded-xl font-sans">قراءة</button>
          </a>
        </div>
      </div>
    ))}
  </div>

  <div className="text-center mt-16">
    <a href="https://www.paypal.com/donate" target="_blank" rel="noopener noreferrer">
      <button className="bg-yellow-500 text-white px-6 py-2 rounded-xl font-sans">تبرع لنا</button>
    </a>
  </div>
</div>

); }

export default App;

