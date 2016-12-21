---
title: "심각한 오류 C1128 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1128"
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

섹션 수가 개체 파일 형식 한도를 초과했습니다. \/bigobj를 사용하여 컴파일하십시오.  
  
 .obj 파일이 허용된 섹션 수, 즉 COFF 개체 파일의 형식 제한을 초과했습니다.  
  
 디버그 빌드에 [\/Gy](../../build/reference/gy-enable-function-level-linking.md)를 사용할 경우 이 섹션 제한을 초과할 수 있습니다. **\/Gy**를 사용하면 함수는 자체의 COMDAT 섹션으로 이동합니다.  디버그 빌드에는 각 COMDAT 함수에 대한 디버그 정보 섹션이 있습니다.  
  
 인라인 함수가 너무 많을 경우에도 C1128 오류가 발생할 수 있습니다.  
  
 이 오류를 해결하려면 소스 파일을 여러 개의 소스 코드 파일로 나눈 다음 **\/Gy**를 사용하지 않고 컴파일하거나[\/bigobj\(.Obj 파일의 섹션 수 늘리기\)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)를 사용하여 컴파일해야 합니다.  **\/Gy**를 사용하여 컴파일하지 않는 경우 최적화를 개별적으로 지정해야 합니다. **\/O2**와 **\/O1**은 모두 **\/Gy**를 내포하고 있기 때문입니다.  
  
 가능한 경우 디버깅 정보 없이 컴파일합니다.  
  
 템플릿의 특정 인스턴스화를 컴파일러에서 자동으로 수행하는 대신 별도의 소스 코드 파일에서 수행해야 할 수도 있습니다.  
  
 코드를 이식할 때, C1128은 x64 컴파일러 및 나중 버전의 x86 컴파일러를 사용할 때 나타날 수 있습니다. x64의 경우는 적어도 템플릿이나 클래스 인라인으로부터 **\/Gy** 또는 인라인으로 컴파일된 함수와 관련된 4개의 영역을 가집니다: 코드, pdata, 디버그 정보 및 가능한 경우 xdata  X86에는 pdata가 없습니다.