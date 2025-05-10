#include <stdio.h>

int main() {
    int w, i, f, frames[50];

    printf("Enter window size: ");
    scanf("%d", &w);

    printf("Enter number of frames to transmit: ");
    scanf("%d", &f);

    printf("Enter %d frames: ", f);
    for (i = 0; i < f; i++)
        scanf("%d", &frames[i]);

    printf("\nWith sliding window protocol:\n");
    for (i = 0; i < f; i++) {
        printf("Sending Frame: %d\n", frames[i]);
        if ((i + 1) % w == 0) {
            printf("Acknowledgment received for above %d frames.\n\n", w);
        }
    }

    if (f % w != 0)
        printf("Acknowledgment received for remaining %d frames.\n", f % w);

    return 0;
}
