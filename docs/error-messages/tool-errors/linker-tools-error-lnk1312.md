---
title: 링커 도구 오류 LNK1312 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 748276ed8fa459c41174f23d32bcef127cbdd510
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1312"></a>링커 도구 오류 LNK1312
잘못 되었거나 손상 된 파일: 어셈블리를 가져올 수 없습니다.  
  
 어셈블리, 모듈 또는 어셈블리를 사용 하 여 컴파일된 이외의 파일을 빌드할 때 **/clr** 에 전달 된는 **/ASSEMBLYMODULE** 링커 옵션입니다.  개체 파일을 전달 하는 경우 **/ASSEMBLYMODULE**만 개체에 직접 전달할을 링커에 대신에 **/ASSEMBLYMODULE**합니다.  
  
## <a name="example"></a>예제  
 다음 샘플.obj 파일이 생성 됩니다.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 LNK1312 합니다.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```