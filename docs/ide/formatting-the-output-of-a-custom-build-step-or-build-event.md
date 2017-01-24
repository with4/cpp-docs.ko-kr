---
title: "사용자 지정 빌드 단계 또는 빌드 이벤트의 출력 형식 지정 | Microsoft Docs"
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
  - "빌드 이벤트[C++], 출력 형식"
  - "빌드 단계[C++], 출력 형식"
  - "빌드[C++], 빌드 이벤트"
  - "빌드[C++], 사용자 지정 빌드 단계"
  - "사용자 지정 빌드 단계[C++], 출력 형식"
  - "이벤트[C++], 빌드"
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 사용자 지정 빌드 단계 또는 빌드 이벤트의 출력 형식 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 지정 빌드 단계나 빌드 이벤트의 출력 형식이 올바르게 지정되어 있으면 다음과 같은 측면에서 매우 유용합니다.  
  
-   경고 및 오류가 **출력** 창에 나열됩니다.  
  
-   출력이 **작업 목록** 창에 나타납니다.  
  
-   **출력** 창에서 출력을 클릭하면 해당 항목이 표시됩니다.  
  
-   F1 키를 사용한 작업을 **작업 목록** 창이나 **출력** 창에서 수행할 수 있습니다.  
  
 출력의 형식은 다음과 같아야 합니다.  
  
 {*filename* \(*line\#* \[, *column\#*\]\) &#124; *toolname*} **:**  
  
 \[*any text*\] {**error** &#124; **warning**} *code\#\#\#\#***:** *localizable string*  
  
 \[ *any text* \]  
  
 다음은 각 항목에 대한 설명입니다.  
  
-   {*a* &#124; *b*}는 *a* 또는 *b* 중 하나를 선택해야 한다는 것을 나타냅니다.  
  
-   \[`ccc`\]는 선택적 문자열 또는 매개 변수입니다.  
  
 예를 들면 다음과 같습니다.  
  
 C:\\*sourcefile.cpp*\(134\) : error C2143: syntax error : missing ';' before '}'  
  
 링크: 심각한 오류 LNK1104: 파일을 열 수 없습니다 '*somelib.lib*'  
  
## 참고 항목  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)