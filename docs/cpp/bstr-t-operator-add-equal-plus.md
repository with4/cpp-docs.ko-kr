---
title: "_bstr_t::operator +=, + | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator+"
  - "_bstr_t::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "+ 연산자, _bstr_t 개체"
  - "+= 연산자, 문자열 추가"
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator +=, +
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_bstr_t` 개체의 끝에 문자를 추가하거나 두 문자열을 연결합니다.  
  
## 구문  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### 매개 변수  
 *s1*  
 `_bstr_t` 개체  
  
 *s2*  
 멀티바이트 문자열입니다.  
  
 `s3`  
 유니코드 문자열입니다.  
  
## 설명  
 이러한 연산자는 다음과 같이 문자열 연결을 수행합니다.  
  
-   **operator\+\=\(**  *s1*  **\)** *s1*의 캡슐화된 `BSTR`에 있는 문자를 이 개체의 캡슐화된 `BSTR`의 끝에 추가합니다.  
  
-   **operator\+\(**  *s1*  **\)** 이 개체의 `BSTR`을 *s1*과 연결하여 형성된 새 `_bstr_t`를 반환합니다.  
  
-   **operator\+\(**  *s2*  **&#124;**  *s1*  **\)** 유니코드로 변환된 멀티바이트 문자열 *s2*를 *s1*에 캡슐화된 `BSTR`과 연결하여 형성된 새 `_bstr_t`를 반환합니다.  
  
-   **operator\+\(**  `s3` **,**  *s1*  **\)** 유니코드 문자열 `s3`을 *s1*에 캡슐화된 `BSTR`과 연결하여 형성된 새 `_bstr_t`를 반환합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)