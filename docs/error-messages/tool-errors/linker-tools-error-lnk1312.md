---
title: "링커 도구 오류 LNK1312 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1312
dev_langs: C++
helpviewer_keywords: LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d7f7b57512f58402403a50bf57176f975769573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1312"></a>링커 도구 오류 LNK1312
잘못 되었거나 손상 된 파일: 어셈블리를 가져올 수 없습니다.  
  
 어셈블리, 모듈 또는 어셈블리를 사용 하 여 컴파일된 이외의 파일을 빌드할 때 **/clr** 에 전달 된는 **/ASSEMBLYMODULE** 링커 옵션입니다.  개체 파일을 전달 하는 경우 **/ASSEMBLYMODULE**만 개체에 직접 전달할을 링커에 대신에 **/ASSEMBLYMODULE**합니다.  
  
## <a name="example"></a>예  
 다음 샘플.obj 파일이 생성 됩니다.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 LNK1312 합니다.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```