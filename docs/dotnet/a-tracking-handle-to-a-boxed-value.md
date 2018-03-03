---
title: "Boxed 값에 대 한 추적 핸들 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: baae8c5317f1e5c9c5acf5bef26a4b79de281a3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>boxed 값에 대한 추적 핸들
참조 값 형식에 대 한 추적 핸들 사용 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 Boxing은 통합 된 CLR 형식 시스템의 평범. 참조 형식에 암시적 쌍은 값 형식 상태로 직접 포함: 관리 되는 힙에 할당 된 명명 되지 않은 개체에 대 한 핸들입니다. 초기화 또는를 입력 한 값이 할당 된 `Object`, 예를 들어에서는 필요-이 이미지의 발생 위치-CLR 힙에 값 형식을 저장 하는 것 먼저 연결된 된 메모리를 할당 하 여 값 형식의 상태를 복사 하 여 를 다음이 익명 값/참조 하이브리드의 주소를 반환 합니다. 따라서 코드가 있습니다. C#  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 많은 진행 코드의 단순성으로 명백한 되기 보다는. C#의 디자인은 뿐만 아니라 어떤 작업 내부적으로 수행 중인 아니라 boxing 자체의 추상화의 복잡성을 숨깁니다. 이 게 효율성에 대해 잘못 된, 명시적 명령을 요구 하 여 사용자의 얼굴에 빌드가 배치 관련된 반면에 c + +에 대 한 확장을 관리 합니다.  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 Boxing은 암시적 Visual c + +에서입니다.  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 `__box` 키워드 사용이 없음 하나 Managed Extensions 내 중요 한 서비스 C# 및 Visual Basic과 같은 언어의 설계: 관리 되는 힙에서 boxed 인스턴스를 직접 조작 하는 것에 대 한 처리는 어휘 및 추적을 제공 합니다. 예를 들어 다음과 같은 작은 프로그램:  
  
```  
int main() {  
   double result = 3.14159;  
   __box double * br = __box( result );  
  
   result = 2.7;   
   *br = 2.17;     
   Object * o = br;  
  
   Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
   Console::WriteLine( S"result :: {0}", __box(result) ) ;  
   Console::WriteLine( S"result :: {0}", br );  
}  
```  
  
 세 가지 호출에 대해 생성 된 기본 코드 `WriteLine` 여기서 보여 각각와 연관 된 오버 헤드 (덕분에 치러야 하기 할에 대 한), boxed 값의 값에 액세스 하는 다양 한 비용 형식 표시 호출 합니다.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
call       void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", __box(result) ) ;  
Ldstr    " result :: {0}"  
ldloc.0  
box    [mscorlib]System.Double // box overhead  
call    void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", br );  
ldstr    "result :: {0}"  
ldloc.0  
call     void [mscorlib]System.Console::WriteLine(string, object)  
```  
  
 Boxed 값 형식에 직접 전달할 `Console::WriteLine` boxing 없어집니다 호출할 필요가 `ToString()`합니다. (물론, 이전의 boxing를 초기화는 `br`이므로 실제로 사용 하지 않으면 어떠한 이점도 없습니다 `br` 작동 하도록 합니다.  
  
 새 구문에서 boxed 값 형식에 대 한 지원 그 성능을 유지 하면서 훨씬 더 유용 하 고 형식 시스템 내에서 통합 됩니다. 예를 들어 다음은 위의 작은 프로그램의 번역이입니다.  
  
```  
int main()  
{  
   double result = 3.14159;  
   double^ br = result;  
   result = 2.7;  
   *br = 2.17;  
   Object^ o = br;  
   Console::WriteLine( "result :: {0}", result.ToString() );  
   Console::WriteLine( "result :: {0}", result );  
   Console::WriteLine( "result :: {0}", br );  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [값 형식 및 동작 (C + + /cli CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [방법: 명시적으로 boxing 요청](../dotnet/how-to-explicitly-request-boxing.md)