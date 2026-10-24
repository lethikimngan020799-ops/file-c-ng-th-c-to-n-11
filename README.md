<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ứng Dụng Ôn Luyện & Theo Dõi Công Thức Toán 11 - THPT Ngô Gia Tự</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- FontAwesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <!-- MathJax for rendering Mathematical Formulas -->
  <script>
    MathJax = {
      tex: {
        inlineMath: [['$', '$'], ['\\(', '\\)']],
        displayMath: [['$$', '$$'], ['[', ']']]
      },
      svg: { fontCache: 'global' }
    };
  </script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
    body { font-family: 'Inter', sans-serif; }
    .hide { display: none !important; }
  </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col">

  <!-- Header / Navigation Bar -->
  <header class="bg-indigo-700 text-white shadow-lg sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-4 py-3 flex justify-between items-center">
      <div class="flex items-center space-x-3">
        <i class="fa-solid me-2 fa-graduation-cap text-2xl text-amber-300"></i>
        <div>
          <h1 class="font-bold text-lg md:text-xl leading-tight">Ghi Nhớ Công Thức Toán 11</h1>
          <p class="text-xs text-indigo-200">Biên soạn theo tài liệu GV. Nguyễn Thanh Nhàn - THPT Ngô Gia Tự</p>
        </div>
      </div>
      
      <!-- Role Switcher -->
      <div class="flex bg-indigo-900/60 p-1 rounded-lg text-sm">
        <button id="btn-role-student" onclick="switchRole('student')" class="px-3 py-1.5 rounded-md font-medium transition-all bg-amber-400 text-slate-900 shadow">
          <i class="fa-solid fa-user-graduate mr-1.5"></i>Học Sinh
        </button>
        <button id="btn-role-teacher" onclick="switchRole('teacher')" class="px-3 py-1.5 rounded-md font-medium transition-all text-indigo-100 hover:text-white">
          <i class="fa-solid fa-chalkboard-user mr-1.5"></i>Giáo Viên
        </button>
      </div>
    </div>
  </header>

  <!-- Main Content Container -->
  <main class="flex-grow max-w-7xl w-full mx-auto p-4 md:p-6">

    <!-- ==================== HỌC SINH VIEW ==================== -->
    <div id="view-student" class="space-y-6">
      
      <!-- Top Student Info Bar -->
      <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-200 flex flex-wrap gap-4 justify-between items-center">
        <div class="flex items-center space-x-3">
          <div class="w-10 h-10 rounded-full bg-indigo-100 text-indigo-600 flex items-center justify-center font-bold">
            <i class="fa-solid fa-user"></i>
          </div>
          <div>
            <span class="text-xs text-slate-500">Tài khoản học sinh:</span>
            <select id="student-selector" onchange="changeStudentProfile(this.value)" class="block text-sm font-bold text-slate-800 bg-transparent border-none focus:ring-0 cursor
