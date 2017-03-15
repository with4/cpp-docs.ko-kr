---
title: "방법: 컨텍스트 클래스를 사용하여 공동 작업 세마포 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "공동 작업 세마포 구현"
  - "context 클래스"
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# 방법: 컨텍스트 클래스를 사용하여 공동 작업 세마포 구현
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 공동 작업 세마포 클래스를 구현 하는 concurrency:: context 클래스를 사용 하는 방법을 보여 줍니다.  
  
  `Context` 클래스를 사용 하면 차단 하거나 현재 실행 컨텍스트를 생성 합니다. 차단 하거나 현재 컨텍스트를 양보 때 유용 현재 컨텍스트는 리소스를 사용할 수 없기 때문에 계속할 수 없습니다. A *세마포* 은 현재 실행 컨텍스트는 리소스를 사용할 수 있을 때까지 기다려야 하는 하나의 상황의 예입니다. 임계 영역 개체와 마찬가지로 세마포는 리소스에 배타적으로 액세스 한 컨텍스트에서 코드를 활성화 하는 동기화 개체입니다. 그러나 임계 영역 개체와 달리 세마포는 리소스에 액세스 하는 동시에 둘 이상의 컨텍스트에 있습니다. 최대 컨텍스트 수 세마포 잠금을 보유 하는 경우 각 추가 컨텍스트 잠금을 해제 하는 다른 컨텍스트의 기다려야 합니다.  
  
### <a name="to-implement-the-semaphore-class"></a>Semaphore 클래스를 구현 하려면  
  
1.  라는 클래스를 선언 `semaphore`합니다. 추가 `public` 및 `private` 이 클래스에는 섹션입니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]  
  
2.  에 `private` 섹션은 `semaphore` 클래스를 선언는 [std:: atomic](../../standard-library/atomic-structure.md) 세마포 카운트를 보유 하는 변수 및 [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) 세마포를 획득 하려고 대기 해야 하는 컨텍스트를 보유 하는 개체입니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]  
  
3.  에 `public` 의 섹션은 `semaphore` 클래스 생성자를 구현 합니다. 사용 하는 생성자는 `long long` 컨텍스트 잠금을 동시에 보유할 수 있는 최대 수를 지정 하는 값입니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]  
  
4.  에 `public` 의 섹션은 `semaphore` 클래스를 구현는 `acquire` 메서드. 원자성 작업으로 세마포 카운트를이 메서드를 감소 시킵니다. 세마포 카운트 음수가 되 면 하는 경우 현재 컨텍스트는 대기 큐와 호출의 끝에 추가 된 [concurrency::Context::Block](../Topic/Context::Block%20Method.md) 메서드를 현재 컨텍스트를 차단 합니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]  
  
5.  에 `public` 의 섹션은 `semaphore` 클래스를 구현는 `release` 메서드. 이 메서드는 원자성 작업으로 세마포 카운트를 증가 시킵니다. 세마포 카운트 증가 연산 전 음수 이면 잠금을 대기 하는 컨텍스트를 하나 이상 있습니다. 이 경우 대기 큐의 앞 부분에 있는 컨텍스트를 차단 해제 합니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]  
  
## <a name="example"></a>예제  
  `semaphore` 때문에이 예제의 클래스는 협조적으로 동작의 `Context::Block` 및 `Context::Yield` 메서드는 런타임에서 다른 작업을 수행할 수 있도록 실행 명령을 내리도록 합니다.  
  
  `acquire` 카운터를 만들었지만 종료 되지 않습니다 다른 컨텍스트를 호출 하기 전에 대기 큐에 컨텍스트를 추가 하는 메서드 감소는 `release` 메서드. 이 고려 하는 `release` 메서드를 호출 하는 스핀 루프를 사용 하 여는 [concurrency::Context::Yield](../Topic/Context::Yield%20Method.md) 때까지 대기 하는 메서드는 `acquire` 메서드 컨텍스트를 추가 완료 합니다.  
  
  `release` 메서드를 호출할 수는 `Context::Unblock` 전에 메서드는 `acquire` 메서드 호출의 `Context::Block` 메서드. 런타임에서 이러한 메서드를 순서에 관계 없이 호출할 수 있으므로이 경합 상태를 방지 하기 위해 필요가 없습니다. 하는 경우는 `release` 메서드 호출 `Context::Unblock` 하기 전에 `acquire` 메서드 호출 `Context::Block` 해당 컨텍스트에 동일한 컨텍스트에 대해 중단 되지 않고 남아 있습니다. 호출할 때마다 런타임만 있으면 `Context::Block` 해당 호출와 일치 하는 `Context::Unblock`합니다.  
  
 다음 예제에서는 전체 `semaphore` 클래스입니다.  `wmain` 함수에서는이 클래스의 기본 사용법을 보여 줍니다.  `wmain` 함수는 [concurrency:: parallel_for](../Topic/parallel_for%20Function.md) 세마포에 대 한 액세스를 필요로 하는 몇 가지 작업을 만들 알고리즘입니다. 3 개의 스레드가 언제 든 지는 잠금을 보유할 수, 때문에 일부 작업을 다른 작업을 마치고 잠금을 해제할 기다려야 합니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]  
  
 이 예제는 다음 예제 출력을 생성 합니다.  
  
```Output  
In loop iteration 5...  
In loop iteration 0...  
In loop iteration 6...  
In loop iteration 1...  
In loop iteration 2...  
In loop iteration 7...  
In loop iteration 3...  
In loop iteration 8...  
In loop iteration 9...  
In loop iteration 4...  
```  
  
 에 대 한 자세한 내용은 `concurrent_queue` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)합니다. 에 대 한 자세한 내용은 `parallel_for` 알고리즘 참조 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `cooperative-semaphore.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 협조적 semaphore.cpp**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 사용할 수는 *리소스 취득은 초기화* (RAII) 패턴에 대 한 액세스를 제한 하는 `semaphore` 개체는 지정 된 범위입니다. RAII 패턴에서 데이터 구조는 스택에 할당 됩니다. 해당 데이터 구조를 초기화 하거나 생성 및 소멸 않았거나 되어 데이터 구조를 소멸 시킬 때 해당 리소스를 해제 하는 경우 리소스를 획득 합니다. RAII 패턴을 포함 하는 범위 종료 전에 소멸자가 호출 보장 합니다. 따라서 리소스 올바르게 관리 되는 예외가 발생 하거나 함수에는 여러 개 포함 된 때 `return` 문입니다.  
  
 라는 클래스를 정의 하는 다음 예제에서는 `scoped_lock`, 에 정의 된는 `public` 의 섹션은 `semaphore` 클래스입니다.  `scoped_lock` 클래스와 유사는 [concurrency::critical_section::scoped_lock](../Topic/critical_section::scoped_lock%20Class.md) 및 [:: scoped_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md) 클래스입니다. 생성자는 `semaphore::scoped_lock` 클래스에 대 한 액세스를 획득는 주어진 `semaphore` 개체와 소멸자가 해당 개체에 대 한 액세스를 해제 합니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]  
  
 에 전달 되는 작업 함수 본문을 수정 하는 다음 예제는 `parallel_for` 알고리즘 사용 하 여 RAII 함수가 반환 되기 전에 세마포를 해제 합니다. 이 기술은 작업 함수를 예외 로부터 안전한 하는지 확인 합니다.  
  
 [!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [컨텍스트](../../parallel/concrt/contexts.md)   
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)

