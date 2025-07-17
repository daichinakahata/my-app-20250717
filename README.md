// src/data/types.ts

export enum TaskStatus {
  NOT_STARTED = '未着手',
  IN_PROGRESS = '進行中',
  COMPLETED = '完了',
  OVERDUE = '期限切れ',
}

export interface Course {
  id: string;
  name: string;
  tasks: Task[]; // 授業に紐づく課題
}

export interface Task {
  id: string;
  courseId: string; // どの授業の課題か
  name: string;
  lectureNumber: string; // 講義回
  deadline: Date;
  status: TaskStatus;
}

export interface Notification {
  id: string;
  message: string;
  timestamp: Date;
  // targetUser: string; // 必要であればユーザーIDなどを追加
  taskId?: string; // どの課題に関する通知か
}
