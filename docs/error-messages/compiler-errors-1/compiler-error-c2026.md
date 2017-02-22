---
title: "컴파일러 오류 C2026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2026"
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열이 너무 길어 뒤에 오는 문자가 잘립니다.  
  
 문자열이 문자 길이 제한인 싱글 바이트 문자 16380개를 넘었습니다.  
  
 인접 문자열을 연결하기에 앞서 해당 문자열은 싱글 바이트 문자 16380개를 넘을 수 없습니다.  
  
 이 길이의 절반에 해당하는 유니코드 문자열 역시 이 오류를 발생시킵니다.  
  
 문자열을 다음과 같이 정의하면 C2026이 발생합니다.  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 이 문자열을 다음과 같이 구분하면 됩니다.  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 32K 이상의 대형 문자열 리터럴은 사용자 지정 리소스나 외부 파일에 예외적으로 저장할 수도 있습니다.  자세한 내용은 [새 사용자 지정 또는 데이터 리소스 만들기](../../mfc/creating-a-new-custom-or-data-resource.md)를 참조하십시오.