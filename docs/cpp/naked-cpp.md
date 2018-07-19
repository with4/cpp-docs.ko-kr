---
title: naked (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- naked_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1057754b5c98086de42daedd5e7aab70656eba69
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943251"
---
# <a name="naked-c"></a>naked(C++)
**Microsoft 전용**  
  
 으로 선언 된 함수에 대 한 합니다 **naked** 특성, 컴파일러가 프롤로그 및 에필로그 코드 없이 코드를 생성 합니다. 이 기능을 이용하여 인라인 어셈블러 코드로 사용자 정의 프롤로그/에필로그 코드 시퀀스를 작성할 수 있습니다. naked 함수는 가상 장치 드라이버 작성에 특히 유용합니다.  유의 합니다 **naked** ARM, x86에만 유효 특성과에서 사용할 수 없는 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>설명  
 때문에 합니다 **naked** 특성 함수 정의에 관련이 없는 형식 한정자를 naked 함수는 확장 된 특성 구문을 사용 해야 합니다 하며 [__declspec](../cpp/declspec.md) 키워드입니다.  
  

 함수는도 표시 하는 경우에 컴파일러는 naked 특성으로 표시 하는 함수에 대 한 인라인 함수를 생성할 수 없습니다는 [__forceinline](inline-functions-cpp.md) 키워드입니다.  

  
 컴파일러에서 오류가 발생 하는 경우는 **naked** 특성 멤버가 아닌 메서드의 정의 이외의 값으로 적용 됩니다.  
  
## <a name="examples"></a>예제  
 이 코드를 사용 하 여 함수 정의 **naked** 특성:  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 또는 또는:  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 합니다 **naked** 특성 특성 함수의 프롤로그 및 에필로그 시퀀스에 대 한 컴파일러의 코드 생성에만 영향을 줍니다. 이러한 함수를 호출하기 위해 생성되는 코드에는 영향을 주지 않습니다. 따라서 합니다 **naked** 특성은 함수 형식의 일부로 간주 되지 않으며 함수 포인터를 사용할 수 없습니다는 **naked** 특성입니다. 또한 합니다 **naked** 특성은 데이터 정의에 적용할 수 없습니다. 예를 들어이 코드 샘플에서는 오류를 생성합니다.  
  
```  
__declspec( naked ) int i;  
// Error--naked attribute not permitted on data declarations.  
```  
  
 합니다 **naked** 특성 함수 정의에 관련 되며, 함수의 프로토타입에 지정할 수 없습니다. 예를 들어이 선언에서는 컴파일러 오류를 생성합니다.  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations  
```  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [Naked 함수 호출](../cpp/naked-function-calls.md)