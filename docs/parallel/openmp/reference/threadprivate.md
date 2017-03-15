---
title: "threadprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "threadprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threadprivate OpenMP directive"
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# threadprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

변수를 스레드를 전용으로 지정 합니다.  
  
## 구문  
  
```  
#pragma omp threadprivate(var)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `var`  
 스레드를 비공개로 할 변수 목록을 쉼표로 구분 합니다.  `var`전역 또는 네임 스페이스\-범위 변수나 정적 로컬 변수 여야 합니다.  
  
## 설명  
 `threadprivate` 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은  [2.7.1 threadprivate 지시문](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 `threadprivate` 지시문 기준의 [스레드](../../../cpp/thread.md)`__declspec` 특성입니다. 제한에서  **\_\_declspec** 적용 `threadprivate`.  
  
 사용할 수 없는 `threadprivate` 를 통해 로드 되는 DLL에서  [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175).  여기에 Dll을 로드 하는 [\/DELAYLOAD\(가져오기 로드 지연\)](../../../build/reference/delayload-delay-load-import.md), 또한 사용 하는  **LoadLibrary**.  
  
 사용할 수 있는 `threadprivate` 프로세스 시작 시 정적으로 로드 된 dll에서입니다.  
  
 때문에 `threadprivate` 기반으로  **\_\_declspec**a `threadprivate` 변수가 병렬 영역에서 생성 된 스레드 팀의 이러한 스레드 뿐 아니라 프로세스에서 시작한 모든 스레드를 존재 합니다.  이렇게 하면, 예를 들어 생성자에 대해 나타날 수 있으므로, 주의 해야 할 세부 구현 되는 `threadprivate` 사용자 정의 형식 이라고 예측 하 고 더 많은.  
  
 A `threadprivate` destructable 형식의 변수를 소멸자가 호출 되도록 보장 되지 않습니다.  예를 들면 다음과 같습니다.  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 사용자에 병렬 영역 구성 스레드를 종료 할 때 컨트롤이 있습니다.  프로세스가 종료 되는 스레드 프로세스 종료에 대 한 알림 메시지가 나타나지 않습니다에 대 한 소멸자가 호출 되지 않습니다 때 이러한 스레드를 존재 하는 경우 `threaded_var` 에서 모든 스레드를 종료 하는 것을 제외 하 고 \(여기서, 주 스레드\).  코드에서 적절 한 파괴를 계산 해야 하므로 `threadprivate` 변수입니다.  
  
## 예제  
 샘플 사용에 대 한 `threadprivate`를 참조 하십시오  [개인](../../../parallel/openmp/reference/private-openmp.md).  
  
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)