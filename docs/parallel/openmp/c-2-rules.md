---
title: "C.2 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C.2 규칙
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표기법은 6.1 C 표준의 섹션에 설명 되어 있습니다. 이 문법 부록 OpenMP C 및 c + + 지시문에 대 한 기본 언어 문법을 확장을 보여 줍니다.  
  
 **/\* c + + (ISO/IEC 14882:1998) \*/**  
  
 *문-seq*:  
  
 *문*  
  
 *openmp 지시문*  
  
 *문-seq 문*  
  
 *문-seq openmp 지시문*  
  
 **/\* C90에서 (ISO/IEC 9899:1990) \*/**  
  
 *문 목록*:  
  
 *문*  
  
 *openmp 지시문*  
  
 *문 목록 문*  
  
 *문 목록 openmp 지시문*  
  
 **/\* C99에서 (ISO/IEC 9899:1999) \*/**  
  
 *블록 항목*:  
  
 *선언*  
  
 *문*  
  
 *openmp 지시문*  
  
 *문*:  
  
 **/\* 표준 문 \*/**  
  
 *openmp 구문*  
  
 *openmp 구문을*:  
  
 *병렬 구문*  
  
 *구문에 대 한*  
  
 *구문 섹션*  
  
 *단일 생성자*  
  
 *구문에 대 한 병렬*  
  
 *병렬 섹션 생성자*  
  
 *마스터 construc*  
  
 *critical 구문*  
  
 *atomic 구문*  
  
 *정렬 된 구문*  
  
 *openmp 지시문*:  
  
 *barrier 지시문*  
  
 *flush 지시문*  
  
 *구조화 된 블록*:  
  
 *문*  
  
 *병렬 구문*:  
  
 *병렬 지시문 구조화 된 블록*  
  
 *병렬 지시문*:  
  
 **# pragma omp 병렬**  *병렬 절*optseq *줄 바꿈*  
  
 *병렬 절*:  
  
 *고유 병렬 절*  
  
 *데이터 절*  
  
 *병렬 절 고유*:  
  
 **경우 (** *식* **)**  
  
 **num_threads (** *식* **)**  
  
 *구문에 대 한*:  
  
 *지시문에 대 한 반복 문*  
  
 *지시문에 대 한*:  
  
 **에 대 한 # pragma omp** *절에 대 한*optseq *줄 바꿈*  
  
 *절에 대 한*:  
  
 *절에 대 한 고유*  
  
 *데이터 절*  
  
 **nowait**  
  
 *절에 대 한 고유*:  
  
 **정렬**  
  
 **일정 (** *일정 종류* **)**  
  
 **일정 (** *일정 종류* **,** *식* **)**  
  
 *일정 종류*:  
  
 **정적**  
  
 **동적**  
  
 **문제 해결**  
  
 **런타임**  
  
 *구문 섹션*:  
  
 *sections 지시문 섹션 범위*  
  
 *sections 지시문*:  
  
 **# pragma omp 섹션** *섹션 절*optseq *줄 바꿈*  
  
 *섹션 절*:  
  
 *데이터 절*  
  
 **nowait**  
  
 *섹션 범위*:  
  
 *{섹션 시퀀스}*  
  
 *섹션 시퀀스*:  
  
 *섹션 지시문*opt *구조화 된 블록*  
  
 *블록-구조 섹션 시퀀스 섹션 지시문*  
  
 *섹션 지시문*:  
  
 **# pragma omp 섹션** *줄 바꿈*  
  
 *단일 구문을*:  
  
 *단일 지시문 구조화 된 블록*  
  
 *단일 지시문*:  
  
 **# pragma omp 단일** *단일 절*optseq *줄 바꿈*  
  
 *단일 절*:  
  
 *데이터 절*  
  
 **nowait**  
  
 *구문에 대 한 병렬*:  
  
 *지시문에 대 한 병렬 반복 문*  
  
 *지시문에 대 한 병렬*:  
  
 **# pragma omp에 대 한 병렬** *절에 대 한 병렬*optseq *줄 바꿈*  
  
 *절에 대 한 병렬*:  
  
 *고유 병렬 절*  
  
 *절에 대 한 고유*  
  
 *데이터 절*  
  
 *병렬 섹션 생성자*:  
  
 *병렬 섹션 지시문 섹션 범위*  
  
 *병렬 섹션 지시문*:  
  
 **# pragma omp 병렬 섹션** *병렬 섹션 절*optseq *줄 바꿈*  
  
 *병렬 섹션 절*:  
  
 *고유 병렬 절*  
  
 *데이터 절*  
  
 *마스터 구문을*:  
  
 *master 지시문 구조화 된 블록*  
  
 *master 지시문*:  
  
 **# pragma omp 마스터** *줄 바꿈*  
  
 *critical 구문*:  
  
 *critical 지시문 구조화 된 블록*  
  
 *critical 지시문*:  
  
 **# pragma omp 중요 한** *지역 구*opt *줄 바꿈*  
  
 *지역 구*:  
  
 *(식별자)*  
  
 *barrier 지시문*:  
  
 **# pragma omp 장벽** *줄 바꿈*  
  
 *atomic 구문*:  
  
 *atomic 지시문 식 문*  
  
 *atomic 지시문*:  
  
 **# pragma omp 원자성** *줄 바꿈*  
  
 *flush 지시문*:  
  
 **# pragma omp 플러시** *플러시 변수*opt *줄 바꿈*  
  
 *플러시 변수*:  
  
 *(변수 목록)*  
  
 *순서가 지정 된 구문을*:  
  
 *정렬 된 지시문 구조화 된 블록*  
  
 *정렬 된 지시문*:  
  
 **# pragma omp 정렬** *줄 바꿈*  
  
 *선언*:  
  
 **/\* 표준 선언 \*/**  
  
 *threadprivate 지시문*  
  
 *threadprivate 지시문*:  
  
 **# pragma omp threadprivate (** *변수 목록*  **)** *줄 바꿈*  
  
 *데이터 절*:  
  
 **개인 (** *변수 목록* **)**  
  
 **copyprivate (**  *변수 목록*  **)**  
  
 **firstprivate (**  *변수 목록*  **)**  
  
 **lastprivate (** *변수 목록*  **)**  
  
 **공유 (** *변수 목록* **)**  
  
 **기본 (공유)**  
  
 **기본값 (없음)**  
  
 **환산 (**  *감소 연산자*  **:**  *변수 목록*  **)**  
  
 **copyin (**  *변수 목록*  **)**  
  
 *감소 연산자*:  
  
 *중 하나*: **+ \* -& ^ & #124; (& a) (& a) (& a) #124; & #124;**  
  
 **/\* C에서 \*/**  
  
 *변수 목록*:  
  
 *식별자*  
  
 *변수 목록* **,** *식별자*  
  
 **/\* c + + \*/**  
  
 *변수 목록*:  
  
 *id 식*  
  
 *변수 목록* **,** *id 식*