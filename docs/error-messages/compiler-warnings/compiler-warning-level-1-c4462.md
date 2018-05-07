---
title: 컴파일러 경고 (수준 1) C4462 | Microsoft Docs
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4462
dev_langs:
- C++
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105a78fe9f8a8d2b6442c9b403af0266de53d3b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4462"></a>컴파일러 경고 (수준 1) C4462

> 형식의 GUID를 확인할 수 없습니다. 프로그램은 런타임에 실패할 수 있습니다.

경고 C4462는 public `TypedEventHandler`의 형식 매개 변수 중 하나가 바깥쪽 클래스에 대한 참조일 때 Windows 런타임 응용 프로그램 또는 구성 요소에서 발생합니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다. 예를 들어를 수준 4 경고로 C4462을 하려면이 줄을 소스 코드 파일을 추가 합니다.

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>예제

이 샘플에서는 C4462 경고를 생성합니다.

```cpp
namespace N
{
       public ref struct EventArgs sealed {};
       public ref struct R sealed
       {
              R() {}
              event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
       };
}

[Platform::MTAThread]
int main()
{
     auto x = ref new N::R();
}
```

오류를 해결하는 방법은 두 가지가 있습니다. 다음 예제에 나오는 한 가지 방법은 다른 Windows 런타임 구성 요소의 코드가 아니라 같은 실행 파일에서 코드를 사용할 수 있도록 이벤트에 내부 액세스 가능성을 부여하는 것입니다.

```cpp
internal:
    event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
```

이벤트가 public이어야 하는 경우 기본 인터페이스를 통해 노출하는 다른 해결 방법을 사용할 수 있습니다.

```cpp
ref struct R;
public interface struct IR{ event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;};

public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR
{
    R() {}
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
};
```

형식 `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^`의 GUID는 다른 구성 요소에서 형식에 액세스할 때만 사용됩니다. 첫 번째 해결 방법이 효과적인 이유는 문제를 해결한 후 고유 구성 요소 내에서만 액세스할 수 있기 때문입니다. 그렇지 않으면 컴파일러는 최악의 경우를 가정하고 경고를 생성합니다.
