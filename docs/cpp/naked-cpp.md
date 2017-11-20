---
title: naked (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: naked_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 587c47370f0bdf80df78896ca5687c4d84f7a83a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="naked-c"></a>naked(C++)
**Microsoft 전용**  
  
 으로 선언 된 함수의 `naked` 특성을 컴파일러 프롤로그 및 에필로그 코드 없이 코드를 생성 합니다. 이 기능을 이용하여 인라인 어셈블러 코드로 사용자 정의 프롤로그/에필로그 코드 시퀀스를 작성할 수 있습니다. naked 함수는 가상 장치 드라이버 작성에 특히 유용합니다.  `naked` 특성은 x86 및 ARM에서만 유효하며 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>설명  
 때문에 `naked` 특성은 함수의 정의에 관련만 하며 형식 한정자, naked 함수는 확장 된 특성 구문을 사용 해야 및 [__declspec](../cpp/declspec.md) 키워드입니다.  
  

 함수는도 표시 하는 경우에 컴파일러는 naked 특성으로 표시 하는 함수에 대 한 인라인 함수를 생성할 수 없습니다는 [__forceinline](inline-functions-cpp.md) 키워드입니다.  

  
 경우 컴파일러는 오류를 발생는 `naked` 특성 이외의 멤버가 아닌 메서드의 정의에 적용 됩니다.  
  
## <a name="examples"></a>예제  
 이 코드를 사용 하는 함수 정의 `naked` 특성:  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 또는 또는:  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 `naked` 특성은 함수의 프롤로그 및 에필로그 시퀀스에 사용되는 컴파일러 코드 생성에만 영향을 줍니다. 이러한 함수를 호출하기 위해 생성되는 코드에는 영향을 주지 않습니다. 따라서 `naked` 특성을 함수 형식의 일부로 간주하지 않으며, 함수 포인터는 `naked` 특성을 가질 수 없습니다. 또한 `naked` 특성은 데이터 정의에 적용될 수 없습니다. 예를 들어이 코드 샘플에서는 오류를 생성합니다.  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 `naked` 특성은 함수 정의에만 관련되며, 함수의 프로토타입에 지정될 수 없습니다. 예를 들어,이 선언은 컴파일러 오류를 일으킵니다.  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [Naked 함수 호출](../cpp/naked-function-calls.md)