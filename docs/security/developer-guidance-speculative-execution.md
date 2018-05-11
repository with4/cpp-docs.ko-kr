---
title: 잘못 된 실행 쪽 채널에 대 한 c + + 개발자 지침 | Microsoft Docs
ms.custom: ''
ms.date: 05/03/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
- Spectre
- CVE-2017-5753
- Speculative Execution
author: mamillmsft
ms.author: mikeblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a7e7ddb51f07f7fe6be1da017d8feae9cc4919e
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>잘못 된 실행 쪽 채널에 대 한 c + + 개발자 지침

이 문서를 식별 하 고 c + + 소프트웨어 추론 실행 측면 채널 하드웨어 취약성을 완화을 지원 하기 위해 개발자를 위한 지침을 포함 합니다. 이 트러스트 경계에 걸쳐 중요 한 정보를 공개할 수 문제와 지침의 잘못 된, 순서가의 실행을 지 원하는 프로세서에서 실행 되는 소프트웨어에 영향을 줄 수 있습니다. 이 클래스의 취약점 년 1 월 2018에 설명 된 첫 번째 및 추가 배경 였으며에서 지침을 확인할 수 있습니다 [Microsoft 보안 권고](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)합니다.

이 문서에서 제공 하는 지침 취약점 CVE-2017-5753, 라고도 유령 variant 1 나타내는 클래스와 관련이 있습니다. 이 하드웨어 취약점 클래스에는 조건부 분기 오측 결과로 발생 하는 추론 실행으로 인해 발생할 수 있는 쪽 채널 관련이 있습니다. Visual Studio 2017 (15.5.5 버전부터 시작)에서 Visual c + + 컴파일러에 대 한 지원에는 `/Qspectre` 스위치 CVE-2017-5753 관련 된 잠재적으로 취약 한 코딩 패턴의 제한 된 집합에 대 한 컴파일 시간 완화를 제공 합니다. 에 대 한 설명서는 [/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) 플래그 효과 및 사용량에 자세한 정보를 제공 합니다. 

추론 실행 측면 채널 취약성에 액세스할 수 있는 소개 라는 프레젠테이션에서 있습니다 [유령의 대/소문자 및 Meltdown](https://www.youtube.com/watch?v=_4O0zMW-Zu4) 이러한 문제를 발견 하는 리서치 팀 중 하나에 의해 합니다.

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>잘못 된 실행 측면 채널 하드웨어 취약성은 무엇입니까?

최신 Cpu를 늘려 더 높은 수준의 성능 제공 지침의 잘못 된 및의 순서가 실행 사용 합니다. 예를 들어 자주 이렇게 지침 실제 분기 대상이 될 때까지 stall 필요 없도록 하는 예측 된 분기 대상에서 추측을 통해 실행을 시작 하는 CPU 수 있는 분기 (조건부 및 indrect)의 대상 예측 확인. CPU를 나중에 오측 발생 했음을 검색, 추측을 통해 계산 된 컴퓨터 상태가 모두 삭제 됩니다. 이렇게 하면 오측된 추론의 구조적 측면에서 볼 수 영향 않으므로.

추론 실행 architecturaly 표시 상태에 영향을 주지 않습니다, 동안 잔여 추적 CPU에서 사용 되는 다양 한 캐시 등의 비 아키텍처 상태에서 비워 둘 수 있습니다. 이러한 잔여 추적 쪽 채널 취약점이 발생할 수 있습니다 추론 실행의 경우 이 더 잘 이해 하려면 CVE 2017 5753 (범위 확인 바이패스)의 예를 제공 하는 다음 코드 조각을 고려 합니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

이 예제에서는 `ReadByte` 은 해당 버퍼에 버퍼, 버퍼 크기 및 인덱스를 제공 합니다. 인덱스 매개 변수에서 지정한 대로 `untrusted_index`, 작음에서 제공 되는 관리자가 아닌 프로세스와 같은 권한 있는 컨텍스트. 경우 `untrusted_index` 는 보다 작은 `buffer_size`, 해당 인덱스에 있는 문자가에서 읽은 다음 `buffer` 되 고 공유에서 참조 하는 메모리 영역에 인덱스에 사용 된 `shared_buffer`합니다.

아키텍처 측면에서 볼 때이 코드 시퀀스는 완벽 하 게 안전 변수 처럼 `untrusted_index` 항상 미만 `buffer_size`합니다. 그러나, 추론 실행 있을 수는 CPU 조건부 분기를 오측 되며 if의 본문을 실행 문의 경우에 `untrusted_index` 보다 크거나 같으면 `buffer_size`합니다. 결과적으로 CPU의 범위에서 일어난 바이트 읽을 추측을 통해 수 `buffer` (암호 일 수 있는)를 통해 후속 부하의 주소를 계산 하는 바이트 값을 사용할 수 없습니다 및 `shared_buffer`합니다. 

잔여 의도 하지 않은 한에서 범위를 벗어난 읽은 바이트 값에 대 한 정보를 제공 하는 CPU 캐시에 남아 있을 수 있습니다 CPU이이 오측 현상을 감지 됩니다, 동안 `buffer`합니다. 이러한 부작용 작음 하 여 검색할 수에서 얼마나 빠르게 검색 하 여 시스템에서 실행 되는 권한 있는 컨텍스트 각 캐시 줄 `shared_buffer` 에 액세스 합니다. 이를 위해 수행할 수 있는 단계는.

1. **호출 `ReadByte` 으로 여러 번 `untrusted_index` 되 고 보다 작은 `buffer_size`** 합니다. 공격 컨텍스트 희생자 컨텍스트를 호출 하면이 `ReadByte` 으로 not 인식 되도록 학습 등 분기 한다고 해 서 예측 되는 예를 들어 (RPC)를 통해 `untrusted_index` 는 보다 작은 `buffer_size`합니다.

2. **모든 캐시 라인 플러시 `shared_buffer`** 합니다. 모든 공유에서 참조 하는 메모리 영역에 캐시 라인 공격 컨텍스트 플러시해야 `shared_buffer`합니다. 간단 하며 같은 내장 함수를 사용 하 여 수행할 수 있습니다이 메모리 영역 전체에서 공유 하므로 `_mm_clflush`합니다.

3. **호출 `ReadByte` 와 `untrusted_index` 보다 크지 `buffer_size`** 합니다. 공격 컨텍스트 희생자 컨텍스트를 호출 하면 `ReadByte` 를 올바르게 예측 하지 분기 수행 되지 것입니다. 이 인해 추측을 통해 if의 본문을 실행할 수 있는 블록 `untrusted_index` 보다 크지 `buffer_size`으로 범위를 벗어나는 읽기 따라서 이어집니다의 `buffer`합니다. 따라서 `shared_buffer` 읽은 범위를 벗어나는, CPU에서 로드할 각 캐시 라인이 모두 오류를 발생 시킬 수 있는 비밀 값을 사용 하 여 인덱싱됩니다.

4. **각 캐시 줄을 읽고 `shared_buffer` 가장 빠르게 액세스 보려면**합니다. 공격 컨텍스트는 각 캐시 라인에 읽을 수 `shared_buffer` 다른 조건들 보다 훨씬 더 빠르게 로드할 수 있는 캐시 줄을 검색 합니다. 3 단계에서 가져온 가능성이 있는 캐시 라인이 모두입니다. 이 예제에서 바이트 값 및 캐시 줄 사이 1:1 관계가 때문 이렇게 하면 공격자가 범위를 벗어나는 읽은 바이트의 실제 값을 유추할 수 있습니다.

위의 CVE-2017-5753 인스턴스의 악용와 함께에서 플러시 + 다시 로드 기술을 사용 하는 예제를 제공 합니다.

## <a name="what-software-scenarios-can-be-impacted"></a>어떤 소프트웨어 시나리오는 영향을 받을 수 있습니까?

와 같은 프로세스를 사용 하는 보안 소프트웨어 개발의 [보안 개발 수명 주기](https://www.microsoft.com/en-us/sdl/) SDL ()가 응용 프로그램에 존재 하는 트러스트 경계를 식별 하는 개발자는 일반적으로 필요 합니다. 트러스트 경계 응용 프로그램 시스템의 다른 프로세스 또는 커널 모드 장치 드라이버의 경우 관리자가 아닌 사용자 모드 프로세스와 같은 신뢰할 수 없는 컨텍스트에 의해 제공 되는 데이터 작용할 수 있는 위치에 있습니다. 새 클래스 추론 실행 쪽 채널을 포함 하는 취약점의 다양 한 코드 및 장치에서 데이터를 격리 하는 기존 소프트웨어 보안 모델의 트러스트 경계와 관련 됩니다.

다음 표에서 이러한 취약점을 발생에 대 한 고려 개발자가 할 수 있는 소프트웨어 보안 모델의 요약을 제공 합니다.

|신뢰 경계|설명|
|----------------|----------------|
|가상 컴퓨터 경계|다른 가상 컴퓨터에서 신뢰할 수 없는 데이터를 수신 하는 별도 가상 컴퓨터에서 작업을 격리 하는 응용 프로그램 공격의 대상이 될 수 있습니다.|
|커널 경계|커널 모드 장치 드라이버 관리자가 아닌 사용자 모드 프로세스에서 신뢰할 수 없는 데이터를 받는 공격의 대상이 될 수 있습니다.|
|프로세스 경계|원격 프로시저 호출 (RPC), 공유 메모리 또는 다른 프로세스 간 통신 (IPC)를 통해 메커니즘 위험에 노출 될 수와 같은 로컬 시스템에서 실행 되는 다른 프로세스에서 신뢰할 수 없는 데이터를 수신 하는 응용 프로그램.|
|영토 경계|받는 트러스트는 영토 외부의 데이터를 위험에 노출 될 수 있습니다 않은 (예: Intel SGX) 보안 영토 내에서 실행 되는 응용 프로그램입니다.|
|언어 경계|해석 하는 응용 프로그램 또는 jit (JUST-IN-TIME)를 컴파일하고 실행으로 작성 된 코드를 신뢰할 수 없는 고급 언어 위험에 노출 될 수 있습니다.|

공격 노출 위에 신뢰 경계를 식별 하 여 가능한 인스턴스의 추론 실행 측면 채널 취약성을 완화 공격 노출 영역에는 코드를 검토 해야이 있는 응용 프로그램입니다. 원격 네트워크 프로토콜 등의 원격 공격 표면을에 노출 하는 신뢰 경계 추론 실행 측면 채널 취약성에 위험에 노출 되도록 설명 하지는 점에 유의 해야 합니다.

## <a name="potentially-vulnerable-coding-patterns"></a>잠재적으로 취약 한 코딩 패턴

추론 실행 측면 채널 취약점 여러 코딩 패턴의 결과로 발생할 수 있습니다. 이 섹션에서는 코딩 잠재적으로 취약 한 패턴을 설명 하 고 각 항목에 대해 예제를 제공 하지만 이러한 테마 변형이 있을 수 인식 되어야 합니다. 따라서 개발자가 모든 잠재적으로 취약 한 코딩 패턴의 단독 목록이 아닌 예제로 이러한 패턴을 수행 하는 것이 좋습니다.

일반적으로 추론 실행 측면 채널 조건부와 관련 된 분기 오측 조건식 제어 하거나 영향을 덜 신뢰 컨텍스트에 의해 수 있는 데이터에 작동 하는 경우 발생할 수 있습니다. 예를 들어에서 사용 하는 조건부 식을 포함할 수 있습니다이 `if`, `for`, `while`, `switch`, 또는 삼항 문의 합니다. 이러한 문은 각각에 대 한 컴파일러는 CPU 수 다음 런타임에 대 한 분기 대상이 예측 하는 조건부 분기를 생성할 수 있습니다.

각 예제에 대 한 "추론 장벽" 라는 구 사용 하 여 주석은 개발자 한 완화 수단으로 장벽 얻는데 이러한 위치에 삽입 됩니다. 이 완화 기능에는 섹션에서 자세히 설명 합니다.

### <a name="speculative-out-of-bounds-load"></a>잘못 된 범위를 벗어나는 로드

이러한 종류의 패턴을 코딩 포함 까지로 연결 되는 잘못 된 범위를 벗어나는 조건부 분기 오측 메모리 액세스 합니다.

#### <a name="array-out-of-bounds-load-feeding-a-load"></a>배열 범위를 벗어나는 로드 부하를 제공 합니다.

이 코딩 방식을 CVE 2017 5753 (범위 확인 바이패스)에 대 한 원래 설명된 취약 코딩 패턴입니다. 이 문서의 백그라운드 섹션에는이 패턴을 자세히 설명합니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

마찬가지로, 부하의 종료를 초과 하는 루프와 함께에서 나타날 수 배열 범위를 벗어나는 오측 인해 조건입니다. 이 예제에서는와 관련 된 조건부 분기는 `x < buffer_size` 식 오측 및 추측을 통해의 본문을 실행 수는 `for` 때 루프 `x` 보다 크거나 같음 `buffer_size`, 따라서 결과에 잘못 된 범위를 벗어나는 로드 합니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

#### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>배열 범위를 벗어나는 로드 간접 분기를 제공 합니다.

이 코딩 방식을 조건부 분기 오측 발생할 수 있는 경우 포함 된 대상에는 간접 분기에는 다음 잠재 고객 주소는 함수 포인터의 배열에 대 한 액세스 범위를 벗어나는 읽어 범위를 벗어나는 합니다. 다음 코드 조각은이 보여 주는 예제를 제공 합니다. 

이 예제에서는 신뢰할 수 없는 메시지 식별자를 통해 DispatchMessage 제공는 `untrusted_message_id` 매개 변수입니다. 경우 `untrusted_message_id` 는 보다 작은 `MAX_MESSAGE_ID`, 함수 포인터의 배열로 인덱싱하고로 분기 하는 데 사용 하는 다음 해당 분기 대상이 있습니다. 이 코드는 구조적으로 안전 하지만 CPU mispredicts 조건부 분기를 하는 경우를 생성할 수 `DispatchTable` 여 `untrusted_message_id` 해당 값 보다 크거나 같음 `MAX_MESSAGE_ID`따라서으로 이어집니다는 범위를 벗어나는 액세스 합니다. 이 추측을 통해 실행 되는 코드에 따라 정보 공개를 야기할 수 있는 배열의 경계를 벗어나 파생 된 분기 대상 주소에서 추론 실행 될 수 있습니다.

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    if (untrusted_message_id < MAX_MESSAGE_ID) {
        // SPECULATION BARRIER
        DispatchTable[untrusted_message_id](buffer, buffer_size);
    }
}
```

배열 범위를 벗어나는 경우와 다른 부하 공급 부하가,이 상태는 오측 인해의 종료 상태를 초과 하는 루프와 함께에서 발생할 수 있습니다.

### <a name="speculative-type-confusion"></a>잘못 된 형식 혼동

이 범주 코딩 패턴의 잘못 된 형식 혼동 하는 조건부 분기 오측을 포함 됩니다. 이 섹션의 코딩 패턴 아래 예제 코드를 참조 합니다.

```cpp
enum TypeName {
    Type1,
    Type2
};

class CBaseType {
public:
    CBaseType(TypeName type) : type(type) {}
    TypeName type;
};

class CType1 : public CBaseType {
public:
    CType1() : CBaseType(Type1) {}
    char field1[256];
    unsigned char field2;
};

class CType2 : public CBaseType {
public:
    CType2() : CBaseType(Type2) {}
    void (*dispatch_routine)();
    unsigned char field2;
};

// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ProcessType(CBaseType *obj)
{
    if (obj->type == Type1) {
        // SPECULATION BARRIER
        CType1 *obj1 = static_cast<CType1 *>(obj);

        unsigned char value = obj1->field2;

        return shared_buffer[value * 4096];
    }
    else if (obj->type == Type2) {
        // SPECULATION BARRIER
        CType2 *obj2 = static_cast<CType2 *>(obj);

        obj2->dispatch_routine();

        return obj2->field2;
    }
}
```

#### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>잘못 된 형식 혼동 하는 범위를 벗어나는 로드

이 코딩 방식을에 잘못 된 형식 혼란이 발생할 수 있는 경우 사례를 포함 한 범위를 벗어나는 또는 여기서 로드 된 값 피드 후속 로드 주소 필드 형식 혼동 액세스 합니다. 이 배열 범위를 벗어나는 코딩 방식을 유사 하지만 위에 표시 된 대로 시퀀스를 코딩 하는 대신 통해 명시 됩니다. 이 예제에서는 공격 컨텍스트 상태가 실행을 위해 컨텍스트를 일으킬 수 `ProcessType` 형식의 개체와 여러 번 `CType1` (`type` 필드가 `Type1`). 첫 번째에 대 한 조건부 분기를 학습의 효과 아무런 `if` 문을 예측할 사용 되지 않습니다. 공격 컨텍스트 교착 상태가 발생 컨텍스트를 실행 하면이 다음 `ProcessType` 형식의 개체와 `CType2`합니다. 첫 번째에 대 한 조건부 분기 하는 경우이 잘못 된 형식 혼동 될 수 있습니다 `if` mispredicts 하 고 본문을 실행 하는 문을 `if` 형식의 개체를 캐스팅 하므로 문을 `CType2` 를 `CType1`합니다. 이후 `CType2` 보다 작으면 `CType1`, 메모리 액세스에 `CType1::field2` 가 결과에 잘못 된 범위를 벗어나는 로드 보안 되지 않은 데이터의 합니다. 이 값은에서 로드 한 다음 사용 `shard_buffer` 배열와 마찬가지로 눈에 띄는 부작용을 만들 수 있는 범위를 벗어나는 예제에서는 앞에서 설명한 합니다.

#### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>잘못 된 형식 혼동 앞에 간접 분기

이 코딩 패턴의 경우 잘못 된 실행 하는 동안 잘못 된 형식 혼동은 안전 하지 않은 간접 분기에서 발생할 수 있는 경우 작업이 포함 됩니다. 이 예제에서는 공격 컨텍스트 상태가 실행을 위해 컨텍스트를 일으킬 수 `ProcessType` 형식의 개체와 여러 번 `CType2` (`type` 필드가 `Type2`). 첫 번째에 대 한 조건부 분기를 학습의 효과 아무런 `if` 수행할 문 및 `else if` 문을 사용해 서 합니다. 공격 컨텍스트 교착 상태가 발생 컨텍스트를 실행 하면이 다음 `ProcessType` 형식의 개체와 `CType1`합니다. 첫 번째에 대 한 조건부 분기 하는 경우이 잘못 된 형식 혼동 될 수 있습니다 `if` 문은 예측 수행 및 `else if` 의 본문을 실행 하므로 문을 예측, 사용은 `else if` 형식의개체로캐스팅하고`CType1` 를 `CType2`합니다. 이후는 `CType2::dispatch_routine` 필드와 겹치는 `char` 배열 `CType1::field1`,이 인해 잘못 된 간접 분기에서 의도 하지 않은 분기 대상에 있습니다. 공격 상황에 맞는 경우 바이트 값을 제어할 수는 `CType1::field1` 배열 수 분기 대상 주소를 제어할 수 있습니다.

## <a name="mitigation-options"></a>완화 옵션

소스 코드를 변경 하 여 추론 실행 측면 채널 취약성을 완화할 수 있습니다. 이러한 변경 내용은 한 취약점의 특정 인스턴스를 추가 하 여과 같은 완화 될 수 있습니다는 *추론 장벽*, 또는 중요 한 정보에 액세스할 수 없도록 추론에 응용 프로그램의 디자인을 변경 하 여 실행 합니다.

### <a name="speculation-barrier-via-manual-instrumentation"></a>수동 계측을 통해 추론 장벽

A *추론 장벽* 아키텍처 경로 따라 진행에서 추론 실행을 방지 하기 위해 개발자가 수동으로 삽입할 수 있습니다. 개발자가 조건부 분기) (이후 블록의 시작 부분에서 조건부 블록의 본문에 위험한 코딩 방식 하기 전에 추론 장벽을 삽입할 수는 예를 들어 또는 관심사 첫 번째 로드 하기 전에. 이렇게 하면 실행을 직렬화 함으로써 아키텍처 경로에서 위험한 코드를 실행할 수 없도록 조건부 분기 오측이 되지 것입니다. 추론 장벽 시퀀스는 다음 표에 설명 된 대로 하드웨어 아키텍처 마다 다릅니다.

|아키텍처|추론 장벽|
|----------------|----------------|
|x86/x64|_mm_lfence()|
|ARM|현재 사용할 수 없음|
|ARM64|현재 사용할 수 없음|


예를 들어 다음과 같은 코드 패턴 완화할 수 있습니다를 사용 하는 `_mm_lfence` 아래와 같이 내장 함수입니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        _mm_lfence();
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>컴파일 타임 계측을 통해 추론 장벽

Visual Studio 2017 (15.5.5 버전부터 시작)에서 Visual c + + 컴파일러에 대 한 지원에는 `/Qspectre` CVE-2017-5753와 관련 된 잠재적으로 취약 한 코딩 패턴의 제한 된 집합에 대 한 추론 장벽을 자동으로 삽입 되는 스위치입니다. 에 대 한 설명서는 [/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) 플래그 효과 및 사용량에 자세한 정보를 제공 합니다. 이 플래그는 잠재적으로 취약 한 코딩 패턴의 모든 포함 하지 않이 되며 따라서 개발자가 사용해 서는 안 것 취약점의이 클래스에 대 한 포괄적인 완화 수단으로 하는 것이 유용 합니다.

### <a name="removing-sensitive-information-from-memory"></a>메모리에서 중요 한 정보를 제거합니다.

추론 실행 측면 채널 취약성을 완화 하기 위해 사용할 수 있는 또 다른 방법은 메모리에서 중요 한 정보를 제거 하는 것입니다. 소프트웨어 개발자가 추론 실행 하는 동안 중요 한 정보를 액세스할 수 있도록 해당 응용 프로그램을 리팩터링 기회 찾을 수 있습니다. 리팩터링 별도 프로세스에 중요 한 정보를 격리 하는 응용 프로그램 디자인에서이 수행할 수 있습니다. 예를 들어 웹 브라우저 응용 프로그램에서 잘못 된 실행을 통해 크로스-원본 데이터에 액세스 하지 못하도록 한 프로세스를 방지 하는 별도 프로세스에 연결 된 각 웹 원본의 데이터를 분리 하려고 할 수 있습니다.

## <a name="see-also"></a>참고 항목

[추론 실행 사이드 채널 취약성을 완화 하기 위해 지침](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)

[추론 실행 측면 채널 하드웨어 취약성 완화](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)
