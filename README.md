#include <stdio.h>
#include <math.h>

// بنية Point: تمثل نقطة (فيها x و y)
struct Point {
    float x;
    float y;
};

// دالة الإزاحة: تحرّك النقطة بـ dx و dy
// نستعمل * (مؤشر) حتى تتغير النقطة الأصلية
void deplacer(struct Point *p, float dx, float dy) {
    p->x = p->x + dx;
    p->y = p->y + dy;
}

// دالة المسافة: تحسب المسافة بين نقطتين
// القانون: racine((x2-x1)² + (y2-y1)²)
float distance(struct Point p1, struct Point p2) {
    float difX = p2.x - p1.x;
    float difY = p2.y - p1.y;
    return sqrt(difX * difX + difY * difY);
}

int main() {
    struct Point p1, p2;
    float dx, dy;

    // 1) التهيئة: نقرأ إحداثيات النقطتين
    printf("P1 (x y) : ");
    scanf("%f %f", &p1.x, &p1.y);

    printf("P2 (x y) : ");
    scanf("%f %f", &p2.x, &p2.y);

    printf("P1 = (%.2f, %.2f)\n", p1.x, p1.y);
    printf("P2 = (%.2f, %.2f)\n", p2.x, p2.y);

    // 2) إزاحة P1: نقرأ dx و dy ثم نستدعي الدالة
    printf("Deplacement de P1 (dx dy) : ");
    scanf("%f %f", &dx, &dy);
    deplacer(&p1, dx, dy);

    printf("P1 apres deplacement = (%.2f, %.2f)\n", p1.x, p1.y);

    // 3) حساب المسافة بين P1 و P2
    printf("Distance P1-P2 = %.2f\n", distance(p1, p2));

    return 0;
}
