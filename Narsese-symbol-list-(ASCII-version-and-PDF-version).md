
![NARS ASCII input table](https://user-images.githubusercontent.com/24262360/51793364-56b02300-218d-11e9-8a28-a0b71146b5d7.png)

[//]: <> ( asdasd )
\documentclass[10pt]{article}
\usepackage{amsmath,amsfonts,amssymb,graphicx,verbatim}
\thispagestyle{empty}

\begin{document}

\begin{center}
 \begin{tabular}{ccccc}
  \hline
  {\bf Type} & {\bf Symbol} & {\bf Input} & {\bf Name} &  {\bf Layer} \\
  \hline

  %=================================================================================
  %=================================================================================

  {\it primary copula} & $\rightarrow$ &  \verb+-->+ &  inheritance &  NAL-1 \\
  {} & $\leftrightarrow$ &  \verb+<->+ &  similarity &  NAL-2 \\
  {} & $\Rightarrow$ &  \verb+==>+ &  implication &  NAL-5 \\
  {} & $\Leftrightarrow$ &  \verb+<=>+ &  equivalence &  NAL-5 \\
  \hline
 
  %=================================================================================
  %=================================================================================
  {\it secondary copula} & $\Leftrightarrow$ &  \verb+{--+ &  instance &  NAL-1 \\
  {} & $\circ \!\! \rightarrow$ &  \verb+--]+ &  property &  NAL-2 \\
  {} & $\rightarrow \!\! \circ$ &  \verb+{-]+ &  instance-property &  NAL-2 \\
  {} & $/ \!\!\! \Rightarrow$ &  \verb+=/>+ &  predictive implication &  NAL-7 \\
  {} & $\setminus \!\!\! \Rightarrow$ &  \verb+=\>+ &  retrospective implication &  NAL-7 \\
  {} & $| \!\!\! \Rightarrow$ &  \verb+=|>+ &  concurrent implication &  NAL-7 \\
  {} & $/ \!\!\! \Leftrightarrow$ &  \verb+</>+ &  predictive equivalence &  NAL-7 \\
  {} & $| \!\!\! \Leftrightarrow$ &  \verb+<|>+ &  concurrent equivalence &  NAL-7 \\
  \hline 
  
  %=================================================================================
  %=================================================================================
  {\it tense} & $/ \!\!\! \Rightarrow$ &  \verb+=/>+ &  future &  NAL-7 \\
  {} & $\setminus \!\!\! \Rightarrow$ &  \verb+=\>+ &  past &  NAL-7 \\
  {} & $| \!\!\! \Rightarrow$ &  \verb+=|>+ &  present &  NAL-7 \\
  \hline
  
  %=================================================================================
  %================================================================================= 
  {\it term connector} & $\{\}$ &  \verb+{ }+ &  extensional set &  NAL-2 \\
  {} & $[ ]$ &  \verb+[ ]+ &  intensional set &  NAL-2 \\
  {} & $\cap$ &  \verb+&+ &  extensional intersection &  NAL-3 \\
  {} & $\cup$ &  \verb+|+ &  intensional intersection &  NAL-3 \\
  {} & $-$ &  \verb+-+ &  extensional difference &  NAL-3 \\
  {} & $\ominus$ &  \verb+~+ &  intensional difference &  NAL-3 \\
  {} & $\times$ &  \verb+*+ &  product &  NAL-4 \\
  {} & $/$ &  \verb+/+ &  extensional image &  NAL-4 \\
  {} & $\setminus$ &  \verb+\+ &  intensional image &  NAL-4 \\
  {} & $\diamond$ &  \verb+_+ &  image place-holder &  NAL-4 \\
  \hline 
  
  %=================================================================================
  %================================================================================= 
  {\it statement connector} & $\neg$ &  \verb+--+ &  negation &  NAL-5 \\
  {} & $\wedge$ &  \verb+&&+ &  conjunction &  NAL-5 \\
  {} & $\vee$ &  \verb+||+ &  disjunction &  NAL-5 \\
  {} & $,$ &  \verb+&/+ &  sequential conjunction &  NAL-7 \\
  {} & $;$ &  \verb+&|+ & parallel conjunction &  NAL-7 \\
  \hline 
  
  %=================================================================================
  %================================================================================= 
  {\it term prefix} & $\#$ &  \verb+#+ &  dependent variable &  NAL-6 \\
  {} & $\$$ &  \verb+$+ &  independent variable &  NAL-6 \\
  {} & $?$ &  \verb+?+ &  query variable &  NAL-6 \\
  {} & $\Uparrow$ &  \verb+^+ &  operator &  NAL-8 \\
  \hline 
  
  %=================================================================================
  %================================================================================= 
  {\it punctuation} & $.$ &  \verb+.+ &  judgment &  NAL-8 \\
  {} & $?$ &  \verb+?+ &  question (on truth-value) &  NAL-8 \\
  {} & $!$ &  \verb+!+ &  goal &  NAL-8 \\
  {} & $\mbox{?`}$ &  \verb+@+ &  quest (on desire-value) &  NAL-8 \\
  \hline 
   \end{tabular}
\end{center}

\end{document}
% vim: shiftwidth=1:
-->