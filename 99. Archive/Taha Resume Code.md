\documentclass[8pt, letterpaper]{article}

% ------------------------ Packages ------------------------
\usepackage[
    ignoreheadfoot,
    top=1.2 cm,
    bottom=1.2 cm,
    left=1.2 cm,
    right=1.2 cm,
    footskip=0.6 cm
]{geometry}
\usepackage{titlesec}
\usepackage{tabularx}
\usepackage{array}
\usepackage[dvipsnames]{xcolor}
\usepackage[
    colorlinks=true,
    linkcolor=black,
    urlcolor=RoyalBlue,
    citecolor=black
]{hyperref}
\definecolor{primaryColor}{RGB}{0, 0, 0}
\usepackage{enumitem}
\usepackage{fontawesome5}
\usepackage{amsmath}

\hypersetup{
    pdftitle={TAHA's Resume},
    pdfauthor={TAHA}
}
\usepackage{eso-pic}
\usepackage{calc}
\usepackage{bookmark}
\usepackage{lastpage}
\usepackage{changepage}
\usepackage{paracol}
\usepackage{ifthen}
\usepackage{needspace}
\usepackage{iftex}

\ifPDFTeX
    \input{glyphtounicode}
    \pdfgentounicode=1
    \usepackage[T1]{fontenc}
    \usepackage[utf8]{inputenc}
    \usepackage{lmodern}
\fi

\usepackage{charter}
\raggedright
\AtBeginEnvironment{adjustwidth}{\partopsep0pt}
\pagestyle{empty}
\setcounter{secnumdepth}{0}
\setlength{\parindent}{0pt}
\setlength{\topskip}{0pt}
\setlength{\columnsep}{0.10cm}
\pagenumbering{gobble}

\titleformat{\section}
    {\needspace{3\baselineskip}\bfseries\normalsize}
    {}
    {0pt}
    {}
    [\vspace{0pt}\titlerule\vspace{0.05cm}]
\titlespacing{\section}{0pt}{0.12 cm}{0.05 cm}

\renewcommand\labelitemi{$\vcenter{\hbox{\small$\bullet$}}$}

\newenvironment{highlights}{
    \begin{itemize}[
        topsep=0pt,
        parsep=0pt,
        itemsep=0pt,
        leftmargin=8pt
    ]
}{
    \end{itemize}
}

\newenvironment{onecolentry}{
    \begin{adjustwidth}{0cm}{0cm}
}{
    \end{adjustwidth}
}

\newenvironment{twocolentry}[2][]{
    \onecolentry
    \def\secondColumn{#2}
    \setcolumnwidth{\fill, 3.6 cm}
    \begin{paracol}{2}
}{
    \switchcolumn \raggedleft \secondColumn
    \end{paracol}
    \endonecolentry
}

\newenvironment{header}{
    \setlength{\topsep}{0pt}\par\kern\topsep\centering\linespread{1.0}
}{
    \par\kern\topsep
}
% ------------------------ Header ------------------------
\begin{document}
\newsavebox\ANDbox
\sbox\ANDbox{$|$}
\newcommand{\AND}{\unskip \cleaders\copy\ANDbox\hskip\wd\ANDbox \ignorespaces}

\begin{header}
    \fontsize{24 pt}{24 pt}\selectfont Taha Hasan Saifee

    \vspace{5 pt}

    \normalsize
    \mbox{New Delhi, India}%
    \kern 5.0 pt%
    \AND%
    \kern 5.0 pt%
    \mbox{\href{mailto:tahahxsxn@gmail.com}{tahahxsxn@gmail.com}}%
    \kern 5.0 pt%
    \AND%
    \kern 5.0 pt%
    \mbox{\href{tel:+91-9910770255}{+91 9910770255}}%
    \kern 5.0 pt%
    \AND%
    \kern 5.0 pt%
    \mbox{\href{https://www.linkedin.com/in/tahahxs/}{linkedin.com/in/tahahxs}}%
    \kern 5.0 pt%

\end{header}



% ------------------------ Summary ------------------------
\vspace{0.1 cm}

\section{Summary}
\begin{onecolentry}
Aspiring developer with hands-on experience in Python and Django. Currently pursuing a B.Tech in Artificial Intelligence and Data Science. Interested in open-source software and building scalable applications.
\end{onecolentry}

\vspace{0.2 cm}
% ------------------------ Education ------------------------
\section{Education}

\begin{onecolentry}
    \textbf{Guru Gobind Singh Indraprastha University}, New Delhi \hfill 2023 -- 2027 \\
    B.Tech in Artificial Intelligence and Data Science
\end{onecolentry}

\vspace{0.1 cm}
\begin{onecolentry}
    \begin{highlights}
        \item CGPA: 8.2
    \end{highlights}
\end{onecolentry}

\vspace{0.1 cm}

% ------------------------ Experience ------------------------
\section{Experience}

\begin{onecolentry}
    \textbf{Software Development Intern}, Tara Applications, New Delhi \hfill December 2025 -- February 2026
\end{onecolentry}

\vspace{0.1 cm}
\begin{onecolentry}
    \begin{highlights}
        \item Built and optimized a Python-based web scraper using Scrapling for collecting publicly available records; enhanced performance using multithreading for concurrent requests.
        \item Automated scraper execution using PowerShell task scheduling, resulting in significant efficiency gains.
        \item Contributed to the development of an internal CRM platform to centralize SMTP-based lead management, reducing manual overhead in the outreach pipeline.
    \end{highlights}
\end{onecolentry}


\vspace{0.2 cm}
% ------------------------ Projects ------------------------

\section{Projects}

\begin{twocolentry}{
    2024
}
    \textbf{CryptFyles — E2EE File Sharing for Teams}
    
    \href{https://github.com/tahahxs/cryptfyles}{\textcolor{RoyalBlue}{github.com/tahahxs/cryptfyles}}
\end{twocolentry}

\vspace{0.1 cm}
\begin{onecolentry}
    \begin{highlights}
        \item Built Django data models for users, groups, and files with clean relationships to organize sharing and permissions.
        \item Implemented role-based access control (RBAC) supporting X user groups and Y+ users per group, ensuring 100\% restricted access to authorized members only
        \item Developed backend features and used Django admin for managing files and groups.
        \item Implemented hybrid encryption pipeline (AES-256 + RSA-2048) enabling secure file storage and key exchange, ensuring end-to-end confidentiality with encrypted key handling per user
        \item Open-source project demonstrating secure and private group file sharing.
    \end{highlights}
\end{onecolentry}



\vspace{0.3 cm}

\begin{twocolentry}{
2025
}
\textbf{LawAIr — AI Legal Assistant}
\end{twocolentry}

\href{https://github.com/tahahxs/LawAIr}{\textcolor{RoyalBlue}{https://github.com/tahahxs/LawAIr}}

\vspace{0.03 cm}
\begin{onecolentry}
\begin{highlights}
\item Built an AI-powered legal assistant using Python, FAISS, and Gemini Pro for semantic search and contextual response generation.
\item Implemented document retrieval using vector embeddings, enabling efficient similarity search over legal data.
\item Developed an interactive Streamlit interface for real-time query handling and user-friendly access to legal insights.
\end{highlights}
\end{onecolentry}

\vspace{0.3 cm}


\begin{twocolentry}{
2024
}
\textbf{Email Spam Classification Using NLP}


\href{https://github.com/tahahxs/Email-Spam-Classifier}{github.com/tahahxs/Email-Spam-Classifier}


\end{twocolentry}

\vspace{0.1 cm}
\begin{onecolentry}
\begin{highlights}
\item Developed a full-stack spam detection web app integrating a self-trained Naive Bayes classifier with NLP preprocessing (tokenization, stopword removal, TF-IDF), achieving real-time classification with 90\%+ accuracy.
\item Built a responsive frontend using Next.js and Tailwind CSS, integrated with a Python Flask REST API backend for live model inference.
\item Covered the complete ML-to-production pipeline — from model training and NLP preprocessing to API integration and deployment on Vercel.
\end{highlights}
\end{onecolentry}


\vspace{0.1 cm}
% ------------------------ Skills ------------------------

\section{Skills}

\begin{onecolentry}
    \textbf{Languages:} C++, Python , JavaScript
\end{onecolentry}

\vspace{0.1 cm}

\begin{onecolentry}
    \textbf{Frameworks:}  Django , React, Express.js, Node.js
\end{onecolentry}

\vspace{0.1 cm}

\begin{onecolentry}
    \textbf{Databases:}  MongoDB, MySQL 
\end{onecolentry}

\vspace{0.1 cm}

\begin{onecolentry}
    \textbf{AI/ML:}  Scikit-learn, NLP, TF-IDF, RAG 
\end{onecolentry}

\vspace{0.1 cm}



\begin{onecolentry}
    \textbf{Tools and Platforms:}  Git \& GitHub, Docker, AWS(Basic) 
\end{onecolentry}

\vspace{0.1 cm}

\begin{onecolentry}
    \textbf{Core Subjects:} Data Structures \& Algorithms, Object-Oriented Programming, DBMS, Cryptography, Computer Networks
\end{onecolentry}



\vspace{0.2 cm}
% ------------------------ Achievements & Certifications ------------------------

\section{Achievements \& Certifications}

\begin{onecolentry}
    \begin{highlights}
        \item Solved 400+ DSA problems on platforms including LeetCode , GeeksforGeeks and CodeChef. 
        \item Earned an IBM Certification in Full Stack Web Development.
    \end{highlights}
\end{onecolentry}

\vspace{0.2 cm}

% ------------------------ End ------------------------
\end{document}