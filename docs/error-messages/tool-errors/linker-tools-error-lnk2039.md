---
title: "링커 도구 오류 LNK2039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2039"
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 링커 도구 오류 LNK2039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ref 클래스를 가져오는\<유형\>' another.obj;에 정의 된 가져온 또는 정의 것  
  
 Ref 클래스의\<`type`\>' 지정 된.obj 파일에서 가져왔지만 다른.obj 파일에 정의 됩니다.  이 상태는 런타임 오류나 기타 예기치 않은 동작이 발생할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  확인 여부를 '`type`'를.obj 파일에 정의 되어 있어야 하 고.winmd 파일에서 가져올 수 있어야 하는지 여부를 확인 합니다.  
  
2.  정의 또는 가져오기를 제거 합니다.  
  
## 참고 항목  
 [링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [링커 도구 오류 LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)