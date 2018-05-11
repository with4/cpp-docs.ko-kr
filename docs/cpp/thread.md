---
title: 스레드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- thread_cpp
dev_langs:
- C++
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0f456d217119020f5683a58560283a1ff08ac75
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="thread"></a>스레드

**Microsoft 전용**

**스레드** 확장된 저장소 클래스 한정자는 스레드 지역 변수를 선언 하는 데 사용 합니다. 이식 가능한 C + + 11에서 지정 된 동일한 및 이후 버전을 사용 하 여는 [thread_local](../cpp/storage-classes-cpp.md#thread_local) 이식 가능한 코드에 대 한 저장소 클래스 지정자. Windows에서 **thread_local** 사용 하 여 구현 **__declspec (thread)** 합니다.

## <a name="syntax"></a>구문

> **__declspec (thread)** *선언 자*  

## <a name="remarks"></a>설명

TLS(스레드 로컬 저장소)는 다중 스레드 프로세스의 각 스레드가 스레드 데이터를 위한 저장소를 할당하는 메커니즘입니다. 표준 다중 스레드 프로그램에서 데이터는 지정된 프로세스의 모든 스레드에서 공유되지만 스레드 로컬 저장소는 스레드별 데이터를 할당하기 위한 메커니즘입니다. 스레드에 대 한 자세한 내용은 참조 하십시오. [다중 스레딩](../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.

스레드 지역 변수 선언을 사용 해야 [확장 특성 구문](../cpp/declspec.md) 및 `__declspec` 키워드는 **스레드** 키워드입니다. 예를 들어, 다음 코드는 정수 스레드 로컬 변수를 선언한 다음 값으로 초기화합니다.

```cpp
__declspec( thread ) int tls_i = 1;
```

동적으로 로드 된 라이브러리의 스레드 로컬 변수를 사용할 때 제대로 초기화 하지 하는 스레드 로컬 변수를 일으킬 수 있는 요소의 알아야 할:

1. 변수가 초기화가 함수 호출 (생성자 포함)로, 해당 이진/dll은 프로세스에 로드 하는 스레드 및 binary/DLL이 로드 된 후에 시작 하는 이러한 스레드에 대 한이 함수 호출 에서만 됩니다. 다른 스레드는 DLL을 로드할 때 이미 실행 중에 대 한 초기화 함수가 호출 되지 않습니다. 동적 초기화 스레드가 시작 될 때 DLL은 프로세스에 없는 경우 메시지 가져옵니다를 되지 DLL_THREAD_ATTACH가 DllMain 호출 하지만 DLL에서 발생 합니다.

1. 상수 값을 사용 하 여 정적으로 초기화 되는 스레드 지역 변수는 일반적으로 모든 스레드에서 올바르게 초기화 됩니다. 그러나 2017 년 12 월을 기준으로에서 없는 경우 알려진된 준수 문제를 그에 따라 수신 constexpr 변수는 Microsoft Visual c + + 컴파일러 정적 초기화 하는 대신 동적

   참고:이 문제를 모두 업데이트 컴파일러의 나중에 수정으로 예상 됩니다.

또한 스레드 로컬 개체 및 변수를 선언 하는 경우 이러한 지침을 준수 해야 합니다.

- 적용할 수는 **스레드** 클래스 및 데이터 선언 및 정의;에 특성 **스레드** 함수 선언 또는 정의에 사용할 수 없습니다.

- 지정할 수는 **스레드** 정적 저장 기간이 있는 데이터 항목에 대해서만 특성입니다. 여기에 전역 데이터 개체 (둘 다 **정적** 및 **extern**), 지역 정적 개체 및 클래스의 정적 데이터 멤버가 있습니다. 자동 데이터 개체를 선언할 수 없습니다는 **스레드** 특성입니다.

- 사용 해야 합니다는 **스레드** 선언 및 정의 동일한 파일 또는 별도 파일에서 발생 하는지 여부를 선언 및 스레드 로컬 개체의 정의 대 한 특성입니다.

- 사용할 수 없습니다는 **스레드** 특성은 형식 한정자로 합니다.

- 사용 하는 개체의 선언 하기 때문에 **스레드** 특성은 허용, 다음 두 예제는 의미는 동일 합니다.

    ```cpp
    // declspec_thread_2.cpp
    // compile with: /LD
    __declspec( thread ) class B {
    public:
       int data;
    } BObject;   // BObject declared thread local.

    class B2 {
    public:
       int data;
    };
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.
    ```

- 표준 C에서는 비정적 범위의 개체에 한해 자신에 대한 참조를 포함하는 식으로 개체 또는 변수를 초기화할 수 있습니다. C++에서는 일반적으로 자신에 대한 참조를 포함하는 식으로 개체를 동적으로 초기화할 수 있지만 스레드 로컬 개체에 대해서는 이렇게 초기화할 수 없습니다. 예를 들어:

   ```cpp
   // declspec_thread_3.cpp
   // compile with: /LD
   #define Thread __declspec( thread )
   int j = j;   // Okay in C++; C error
   Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
   ```

   한 **sizeof** 초기화 되는 개체를 포함 하는 식 자체에 대 한 참조를 구성 하지 않으며과 C와 c + +에서 허용 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)  
[키워드](../cpp/keywords-cpp.md)  
[TLS(스레드 로컬 저장소)](../parallel/thread-local-storage-tls.md)  
