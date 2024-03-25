#include <iostream>
#include <fstream>
#include <iomanip>

const int MAX_SIZE = 10;

void readMatrix(int matrix[MAX_SIZE][MAX_SIZE], int& size, std::ifstream& file) {
    file >> size;
    for (int i = 0; i < size; ++i) {
        for (int j = 0; j < size; ++j) {
            file >> matrix[i][j];
        }
    }
}

void printMatrix(int matrix[MAX_SIZE][MAX_SIZE], int size) {
    for (int i = 0; i < size; ++i) {
        for (int j = 0; j < size; ++j) {
            std::cout << std::setw(4) << matrix[i][j];
        }
        std::cout << std::endl;
    }
}

void addMatrices(int matrix1[MAX_SIZE][MAX_SIZE], int matrix2[MAX_SIZE][MAX_SIZE], int result[MAX_SIZE][MAX_SIZE], int size) {
    for (int i = 0; i < size; ++i) {
        for (int j = 0; j < size; ++j) {
            result[i][j] = matrix1[i][j] + matrix2[i][j];
        }
    }
}

void multiplyMatrices(int matrix1[MAX_SIZE][MAX_SIZE], int matrix2[MAX_SIZE][MAX_SIZE], int result[MAX_SIZE][MAX_SIZE], int size) {
    for (int i = 0; i < size; ++i) {
        for (int j = 0; j < size; ++j) {
            result[i][j] = 0;
            for (int k = 0; k < size; ++k) {
                result[i][j] += matrix1[i][k] * matrix2[k][j];
            }
        }
    }
}

void subtractMatrices(int matrix1[MAX_SIZE][MAX_SIZE], int matrix2[MAX_SIZE][MAX_SIZE], int result[MAX_SIZE][MAX_SIZE], int size) {
    for (int i = 0; i < size; ++i) {
        for (int j = 0; j < size; ++j) {
            result[i][j] = matrix1[i][j] - matrix2[i][j];
        }
    }
}

void updateElement(int matrix[MAX_SIZE][MAX_SIZE], int size, int row, int col, int newValue) {
    if (row >= 0 && row < size && col >= 0 && col < size) {
        matrix[row][col] = newValue;
    }
}

int getMaxValue(int matrix[MAX_SIZE][MAX_SIZE], int size) {
    int maxVal = matrix[0][0];
    for (int i = 0; i < size; ++i) {
        for (int j = 0; j < size; ++j) {
            if (matrix[i][j] > maxVal) {
                maxVal = matrix[i][j];
            }
        }
    }
    return maxVal;
}

void transposeMatrix(int matrix[MAX_SIZE][MAX_SIZE], int size) {
    int temp;
    for (int i = 0; i < size; ++i) {
        for (int j = i + 1; j < size; ++j) {
            temp = matrix[i][j];
            matrix[i][j] = matrix[j][i];
            matrix[j][i] = temp;
        }
    }
}

int main() {
    std::ifstream inputFile("matrix_input.txt");
    if (!inputFile) {
        std::cerr << "Error: Unable to open file." << std::endl;
        return 1;
    }

    int size;
    int matrix1[MAX_SIZE][MAX_SIZE];
    int matrix2[MAX_SIZE][MAX_SIZE];
    int result[MAX_SIZE][MAX_SIZE];

    readMatrix(matrix1, size, inputFile);
    readMatrix(matrix2, size, inputFile);

    std::cout << "Matrix 1:" << std::endl;
    printMatrix(matrix1, size);

    std::cout << "\nMatrix 2:" << std::endl;
    printMatrix(matrix2, size);

    std::cout << "\nMatrix 1 + Matrix 2:" << std::endl;
    addMatrices(matrix1, matrix2, result, size);
    printMatrix(result, size);

    std::cout << "\nMatrix 1 * Matrix 2:" << std::endl;
    multiplyMatrices(matrix1, matrix2, result, size);
    printMatrix(result, size);

    std::cout << "\nMatrix 1 - Matrix 2:" << std::endl;
    subtractMatrices(matrix1, matrix2, result, size);
    printMatrix(result, size);

    std::cout << "\nEnter row, column, and new value to update Matrix 1: ";
    int row, col, newValue;
    std::cin >> row >> col >> newValue;
    updateElement(matrix1, size, row, col, newValue);

    std::cout << "\nMatrix 1 after update:" << std::endl;
    printMatrix(matrix1, size);

    std::cout << "\nMax value in Matrix 1: " << getMaxValue(matrix1, size) << std::endl;

    std::cout << "\nTranspose of Matrix 1:" << std::endl;
    transposeMatrix(matrix1, size);
    printMatrix(matrix1, size);

    return 0;
}
