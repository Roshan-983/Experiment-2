# Experiment-2

#include <stdio.h>

#define MAX_SIZE 100

int main() {
    int arr[MAX_SIZE], size = 0, choice, i, pos, element;

    while (1) {
        printf("\nMenu:\n");
        printf("1. Insert Element\n");
        printf("2. Delete Element\n");
        printf("3. Display Elements\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
        case 1:
            if (size >= MAX_SIZE) {
                printf("Array is full!\n");
                break;
            }
            printf("Enter position (0 to %d): ", size);
            scanf("%d", &pos);
            if (pos < 0 || pos > size) {
                printf("Invalid position!\n");
                break;
            }
            printf("Enter element to insert: ");
            scanf("%d", &element);
            for (i = size; i > pos; i--)
                arr[i] = arr[i - 1];
            arr[pos] = element;
            size++;
            printf("Element inserted.\n");
            break;

        case 2:
            if (size == 0) {
                printf("Array is empty!\n");
                break;
            }
            printf("Enter position to delete (0 to %d): ", size - 1);
            scanf("%d", &pos);
            if (pos < 0 || pos >= size) {
                printf("Invalid position!\n");
                break;
            }
            for (i = pos; i < size - 1; i++)
                arr[i] = arr[i + 1];
            size--;
            printf("Element deleted.\n");
            break;

        case 3:
            if (size == 0) {
                printf("Array is empty!\n");
            } else {
                printf("Array elements: ");
                for (i = 0; i < size; i++)
                    printf("%d ", arr[i]);
                printf("\n");
            }
            break;

        case 4:
            printf("Exiting...\n");
            return 0;

        default:
            printf("Invalid choice! Try again.\n");
        }
    }

    return 0;
}
