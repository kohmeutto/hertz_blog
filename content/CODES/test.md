#include <stdio.h>

// 클래스 기본 구조
typedef struct LSI LSI;
struct LSI {
    // properties
    int h[3];

    // methods
    void (*LSIFnc)(const LSI *self, int *cause, int *result);
};

// 클래스 메서드 정의
static void Convolution(const LSI *self, int *cause, int *result) {
    for (int i = 0; i < 3; i++) {
        result[i] = self->h[i] * cause[i];
    }
}

// 객체 생성
static const LSI edge = { {1, 0, -1}, Convolution };

// main
int main(void) {
    int cause[3] = {5, 6, 7};
    int result[3];

    edge.LSIFnc(&edge, cause, result);
    for (int i = 0; i < 3; i++) printf("%d\n", result[i]);

    return 0;
}