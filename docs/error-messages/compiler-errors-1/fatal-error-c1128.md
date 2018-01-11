---
title: "심각한 오류 C1128 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1128
dev_langs: C++
helpviewer_keywords: C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22b53914fba8ab5d5c31d8f7ed0a2e3db52aad5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1128"></a>심각한 오류 C1128
섹션 수가 개체 파일 형식 한도 초과 했습니다: /bigobj를 사용 하 여 컴파일  
  
 COFF 개체 파일 형식 제한의 허용 가능한 섹션의 수를 초과 하는.obj 파일.  
  
 이 섹션 제한을 사용 하 여 발생할 수 있습니다 [/Gy](../../build/reference/gy-enable-function-level-linking.md) 및 디버그 빌드에 있습니다. **/Gy** 사용 하면 함수는 자신의 COMDAT 섹션으로 이동 합니다. 디버그 빌드에서 각 COMDAT 함수에 대 한 디버그 정보 섹션이 있습니다.  
  
 C1128은 인라인 함수가 너무 많을 경우에 발생할 수 있습니다.  
  
 이 오류를 해결 하려면 여러 소스 코드 파일에 소스 파일을 나눌, 하지 않고 컴파일할 **/Gy**를 사용 하 여 컴파일 또는 [/bigobj (섹션 수 늘리기에 있습니다. Obj 파일)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)합니다.  로 컴파일하지 않습니다 경우 **/Gy**, 최적화를 개별적으로 지정 해야 합니다 이후 **/O2** 및 **/O1** 의미 둘 다 **/Gy**합니다.  
  
 가능 하면 정보를 디버깅 하지 않고 컴파일하십시오.  
  
 중에 내보낼 컴파일러 하지 않고 별도 소스 코드 파일에서 서식 파일의 특정 인스턴스화를 포함 하도록 할 수도 있습니다.  
  
 코드를 이식 C1128 가능성이 먼저 표시 됩니다는 x64를 사용 하는 경우, 컴파일러 및 x86 훨씬 나중 컴파일러입니다. x64 컴파일된 각 함수에 연결 된 4 단원 갖습니다 **/Gy** 템플릿이나 인라인 클래스에서 인라인: 코드를 pdata를 복사해 정보 및 xdata 디버그 합니다.  X86 pdata가 없습니다.