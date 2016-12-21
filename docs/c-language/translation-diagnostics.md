---
title: "변환: 진단 | Microsoft Docs"
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
  - "C"
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 변환: 진단
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 2.1.1.3** 진단 식별 방법  
  
 Microsoft C는 다음의 경우에 형식에서 오류 메시지를 생성합니다.  
  
```  
  
filename( line-number ) : diagnostic Cnumber message  
```  
  
 파일 이름이 오류가 발견된 소스 파일의 이름일 경우, 줄 번호가 컴파일러 오류가 발견된 줄 번호일 경우, `diagnostic`이 "오류" 또는 "경고"일 경우, `number`가 오류 또는 경고를 식별하는 고유한 네 자리 디지털 숫자\(**C** 뒤에 위치, 구문 설명 참조\)일 경우, `message`가 설명 메시지일 경우입니다.  
  
## 참고 항목  
 [구현이 정의된 동작](../c-language/implementation-defined-behavior.md)