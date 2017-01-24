---
title: "템플릿 지시문 | Microsoft Docs"
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
helpviewer_keywords: 
  - "[!else] 템플릿 지시문"
  - "[!endif] 템플릿 지시문"
  - "[!endloop] 템플릿 지시문"
  - "[!if] 템플릿 지시문"
  - "[!loop] 템플릿 지시문"
  - "[!output] 템플릿 지시문"
  - "사용자 지정 마법사, 템플릿 지시문"
  - "지시문, 템플릿 지시문"
  - "else 지시문([!else])"
  - "endif 지시문([!endif])"
  - "endloop 지시문([!endloop])"
  - "if 지시문([!if])"
  - "loop 지시문([!loop])"
  - "output 지시문([!output])"
  - "템플릿 지시문"
ms.assetid: b6204153-813a-423c-b044-e39c352cc5af
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 템플릿 지시문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사 [템플릿 파일](../ide/template-files.md)과 [Templates.inf 파일](../ide/templates-inf-file.md)에서 다음과 같은 템플릿 지시문을 사용하여 마법사를 사용자 지정할 수 있습니다.  
  
|지시문|설명|  
|---------|--------|  
|\[\!  If|조건을 검사하는 컨트롤 구조를 시작합니다.|  
|\[\!  else \]|\[\! if\] 컨트롤 구조에 포함되는  부분입니다.  다른 조건을 검사합니다.|  
|\[\!  endif\]|\[\! output\] 컨트롤 구문의 정의를  부분입니다.|  
|\[\!  끝냅니다.|다음 두 가지 방법으로 사용할 수 있습니다.<br /><br /> -   \[\!  output "string"\]을 사용하면 문자열이 출력됩니다.<br />-   \[\!  output SYMBOL\_STRING\]을 사용하면 SYMBOL\_STRING 기호의 값이 출력됩니다.|  
|\[\!  loop\]|다음 두 가지 방법으로 사용할 수 있습니다.<br /><br /> -   \[\!  loop \= 5\]<br />-   \[\!  loop \= *NUM\_OF\_PAGES*\]. 여기서 *NUM\_OF\_PAGES*는 숫자 값이 있는 기호입니다.|  
|\[\!  endloop\]|루프 구조를 끝냅니다.|  
  
 왼쪽 대괄호\(\[\) 다음에 바로 느낌표\(\!\)가 오면 템플릿 지시문의 시작을 나타냅니다.  오른쪽 대괄호는 템플릿 지시문의 끝을 나타냅니다.  다음은 필수 구문입니다.  
  
```  
[!directive params]  
```  
  
 공백이나 식별자가 아닌 문자는 *directive*와 *params* 사이에만 필요합니다.  
  
## 예제  
  
```  
[!if SAMPLE_RADIO_OPTION1]  
You have checked the option 'Sample radio button option 1'  
[!else]  
You have checked the option 'Sample radio button option 2'  
[!endif]  
```  
  
 템플릿 파일에서 위의 지시문에 다음과 같은 연산자를 사용할 수 있습니다.  
  
```  
+  
-     
=  
!=     
==     
||     
&&    
!  
```  
  
## 예제  
  
```  
[!if SYMBOL_STRING != 0]  
```  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)